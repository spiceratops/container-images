FROM mcr.microsoft.com/dotnet/sdk:8.0-bookworm-slim

ARG UID=1000
ARG VERSION

RUN apt update
RUN apt install -y git wget build-essential python3.11 python3.11-venv python3.11-dev ffmpeg

RUN apt install -y libglib2.0-0 libgl1

RUN \
git clone --recurse-submodules --branch ${VERSION} --single-branch https://github.com/mcmonkeyprojects/SwarmUI.git /SwarmUI

RUN chown -R $UID:$UID /SwarmUI

RUN git config --global --add safe.directory '*'

EXPOSE 7801

ENTRYPOINT ["bash", "/SwarmUI/launchtools/docker-standard-inner.sh"]

LABEL org.opencontainers.image.source="https://github.com/mcmonkeyprojects/SwarmUI"
