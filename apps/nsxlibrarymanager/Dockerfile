FROM ghcr.io/ivaano/nsxlibrarymanager:0.4.2
WORKDIR /app

RUN chown 1000:1000 /app -R

USER 1000
EXPOSE 8080

ENTRYPOINT ["dotnet", "NsxLibraryManager.dll"]

LABEL org.opencontainers.image.source="https://github.com/ivaano/NsxLibraryManager"
