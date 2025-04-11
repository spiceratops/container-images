FROM mcr.microsoft.com/dotnet/sdk:8.0-bookworm-slim

ARG UID=1000
ARG VERSION

RUN apt update
RUN apt install -y git wget build-essential python3.11 python3.11-venv python3.11-dev ffmpeg

RUN apt install -y libglib2.0-0 libgl1

ADD https://github.com/mcmonkeyprojects/SwarmUI.git#${VERSION} /app

RUN chown -R $UID:$UID /app

RUN git config --global --add safe.directory '*'

EXPOSE 7801

ENTRYPOINT ["bash", "/app/launchtools/docker-standard-inner.sh"]

LABEL org.opencontainers.image.source="https://github.com/mcmonkeyprojects/SwarmUI"
