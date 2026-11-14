# Copyright (c) 2026 TrueSignal Deception. All rights reserved.
#
# Hub image. Build from the repository root AFTER building the admin UI
# (`make ui`), which writes hub/internal/webui/dist/ for go:embed:
#   docker build -f hub/Dockerfile --build-arg VERSION=3.0.0 -t ts-hub .
# Cross-compiles on the build platform (no emulation) for TARGETARCH.
# Base images are pinned by digest; bump them deliberately.

FROM --platform=$BUILDPLATFORM golang:1.27.4-bookworm@sha256:4fa7c968ba93f1635670522dbb01a2c78150443e1385746924566079f36570ea AS build
ARG TARGETOS=linux
ARG TARGETARCH
ARG VERSION
WORKDIR /src
COPY sdk/go/ sdk/go/
COPY hub/ hub/
WORKDIR /src/hub
ENV CGO_ENABLED=0 GOFLAGS=-trimpath GOWORK=off
RUN test -f internal/webui/dist/index.html || { echo "admin UI not built: run make ui first" >&2; exit 1; }
RUN test -n "$VERSION" && grep -q "^var Version = \"$VERSION\"$" cmd/truesignal-hub/main.go \
	|| { echo "VERSION build arg must equal the Version in cmd/truesignal-hub/main.go" >&2; exit 1; }
RUN mkdir -p /out/data && GOOS=$TARGETOS GOARCH=$TARGETARCH go build -ldflags='-s -w -buildid=' -o /out/truesignal-hub ./cmd/truesignal-hub

FROM gcr.io/distroless/static-debian12:nonroot@sha256:afa5c872c891853ca7fcf1f12c3edb23f7eeef36189728842dd51042ff57f7ab
ARG VERSION
LABEL org.opencontainers.image.title="TrueSignal Hub" \
      org.opencontainers.image.version="$VERSION" \
      org.opencontainers.image.source="https://github.com/mahmoudahmed3132/TrueSignal-Rewrite"
COPY --from=build /out/truesignal-hub /truesignal-hub
COPY --from=build --chown=65532:65532 /out/data /data
USER 65532:65532
VOLUME ["/data"]
EXPOSE 8080
ENTRYPOINT ["/truesignal-hub"]
CMD ["serve"]
