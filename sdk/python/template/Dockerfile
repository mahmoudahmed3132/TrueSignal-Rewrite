# Copyright (c) 2026 TrueSignal Deception. All rights reserved.
#
# Python template sensor. Build from the repository root:
#   docker build -f sdk/python/template/Dockerfile -t ts-sensor-python-template .
# Distroless Python (no shell, non-root); pinned by digest, bump deliberately.
FROM gcr.io/distroless/python3-debian13:nonroot@sha256:6c4cb3bfa4b555429dd19541796a6ba6b30c84675b460bd0bd5072f7d5bdae71
WORKDIR /app
COPY sdk/python/truesignal_sdk/ /app/truesignal_sdk/
COPY sdk/python/template/sensor.py /app/sensor.py
ENV PYTHONDONTWRITEBYTECODE=1 PYTHONUNBUFFERED=1
USER 65532:65532
ENTRYPOINT ["python3", "/app/sensor.py"]
