# Copyright (c) 2026 TrueSignal Deception. All rights reserved.
#
# Build from the repository root:
#   docker build -f sensors/web-router-decoy/Dockerfile -t ts-sensor-web-router-decoy .
# Base images are pinned by digest; bump them deliberately.

FROM golang:1.27.4-bookworm@sha256:4fa7c968ba93f1635670522dbb01a2c78150443e1385746924566079f36570ea AS build
WORKDIR /src
COPY sdk/go/ sdk/go/
COPY sensors/web-router-decoy/ sensors/web-router-decoy/
WORKDIR /src/sensors/web-router-decoy
ENV CGO_ENABLED=0 GOFLAGS=-trimpath GOWORK=off
RUN go build -ldflags='-s -w -buildid=' -o /out/sensor .

FROM gcr.io/distroless/static-debian12:nonroot@sha256:afa5c872c891853ca7fcf1f12c3edb23f7eeef36189728842dd51042ff57f7ab
COPY --from=build /out/sensor /sensor
USER 65532:65532
ENTRYPOINT ["/sensor"]
