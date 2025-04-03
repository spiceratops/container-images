FROM ghcr.io/ivaano/nsxlibrarymanager:v0.4.4

RUN chown 1000:1000 /app -R

USER 1000
WORKDIR /app
EXPOSE 8080

ENTRYPOINT ["dotnet", "NsxLibraryManager.dll"]

LABEL org.opencontainers.image.source="https://github.com/ivaano/NsxLibraryManager"
