# Upgrade the helm client version here when the az cluster tiller version
# upgrades.
FROM lachlanevenson/k8s-helm:v2.13.1

FROM lachlanevenson/k8s-kubectl:v1.14.1

FROM microsoft/azure-cli:latest
COPY --from=0 /usr/local/bin/helm /usr/local/bin/helm
COPY --from=1 /usr/local/bin/kubectl /usr/local/bin/kubectl
