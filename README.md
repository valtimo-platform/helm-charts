# Valtimo Cloud Helm charts
This repository contains the helm charts for the Valtimo application.

We maintain three branches, `release/1.x.x`, `release/2.x.x` and `main` that are compatible with respectively Valtimo 10.x, 11.x and 12.x.
Please pick the right chart version to ensure the proper configmap/envvars are setup in your cluster.

Compatibility matrix for Valtimo-Backend:

![img.png](img.png)

Find the helm configuration values here:

* [Valtimo Backend](https://github.com/valtimo-platform/helm-charts/blob/main/charts/valtimo-backend/valtimo-backend/README.md)
* [Valtimo Frontend](https://github.com/valtimo-platform/helm-charts/blob/main/charts/valtimo-frontend/valtimo-frontend/README.md)

The generated list of published helm releases can be found [here](https://raw.githubusercontent.com/valtimo-platform/helm-charts/refs/heads/gh-pages/index.yaml).

