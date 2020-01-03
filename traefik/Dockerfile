ARG BUILD_IMAGE
ARG BASE_IMAGE

FROM $BUILD_IMAGE as build
FROM $BASE_IMAGE

COPY --from=build /windows/system32/netapi32.dll /windows/system32/netapi32.dll

ENV TRAEFIK_VERSION 1.7.20

ADD https://github.com/containous/traefik/releases/download/v${TRAEFIK_VERSION}/traefik_windows-amd64.exe C:\\traefik.exe

ENTRYPOINT ["C:\\traefik.exe"]
