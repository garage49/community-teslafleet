# Runtime image for the garage49 build farm (go-build.yml, docker-context
# deployment/docker). It compiles nothing: the farm builds the static gateway
# binary once and copies it to docker-bin/gateway, so the image carries the
# same bytes as the workflow artifact. Upstream's root Dockerfile is left as it
# is for docker compose and GHCR.
FROM gcr.io/distroless/static-debian12:nonroot
COPY docker-bin/gateway /gateway
# Defaults; override with TGW_* env or a mounted /config/config.yaml
ENV TGW_CONFIG=/config/config.yaml
USER 65532:65532
EXPOSE 4460
ENTRYPOINT ["/gateway"]
