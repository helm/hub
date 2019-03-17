# Upgrade the helm client version here when the az cluster tiller version
# upgrades.
ARG TAG=v2.13.1
FROM lachlanevenson/k8s-helm:${TAG} as build

FROM microsoft/azure-cli:latest
COPY --from=build /usr/local/bin/helm /usr/local/bin/helm
