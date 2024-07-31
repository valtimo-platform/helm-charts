# valtimo-backend

![Version: 0.1.9](https://img.shields.io/badge/Version-0.1.9-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.1.0](https://img.shields.io/badge/AppVersion-0.1.0-informational?style=flat-square)

A Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| oci://registry-1.docker.io/bitnamicharts | keycloak | ~15.1.2 |
| oci://registry-1.docker.io/bitnamicharts | mysql | ~9.10.1 |
| oci://registry-1.docker.io/bitnamicharts | postgresql | ~12.5.6 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity for Valtimo-backend pods assignment  |
| autoscaling.enabled | bool | `false` | Enable/disable autoscaling for the Valtimo-backend deployment |
| autoscaling.maxReplicas | int | `100` | Maximum replicas for the Valtimo-backend deployment |
| autoscaling.minReplicas | int | `1` | Minimum replicas for the Valtimo-backend deployment |
| autoscaling.targetCPUUtilizationPercentage | int | `80` | Valtimo-backend Deployment autoscaling target CPU percentage |
| autoscaling.targetMemoryUtilizationPercentage | int | `80` | Valtimo-backend Deployment autoscaling target Mem utilization percentage |
| existingSecret | string | `nil` | Refer to an existing secret to avoid managing secrets through Helm. |
| extraEnvVars | list | `[]` | Array with extra environment variables to add |
| extraEnvironmentVariables | list | `[]` |  |
| extraVolumeMounts | list | `[]` | Optionally specify extra list of additional volumeMounts |
| extraVolumes | list | `[]` | Optionally specify extra list of additional volumes |
| fullnameOverride | string | `""` | String to fully override valitmo-backend.fullname |
| image.pullPolicy | string | `"IfNotPresent"` | Pull policy for the image |
| image.repository | string | `""` | Domain of the image repository |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | Image pull secrets |
| ingress.annotations | object | `{}` | Ingress annotations |
| ingress.className | string | `""` | Ingress Class which will be used to implement the Ingress |
| ingress.enabled | bool | `false` | Expose the Valtimo-backend UI through an ingress |
| ingress.hosts[0] | object | `{"host":"chart-example.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}` | Ingress hostname |
| ingress.hosts[0].paths[0] | object | `{"path":"/","pathType":"ImplementationSpecific"}` | Ingress path |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` | Ingress path type |
| ingress.tls | list | `[]` | Enable TLS for the Ingress |
| keycloak | object | `{"auth":{"adminPassword":"","adminUser":"user","existingSecret":""}}` | Keycloak subchart by Bitnami. See https://artifacthub.io/packages/helm/bitnami/keycloak?modal=values for all possible values |
| livenessProbe.failureThreshold | int | `6` | Failure threshold for livenessProbe |
| livenessProbe.initialDelaySeconds | int | `40` | Initial delay seconds for livenessProbe |
| livenessProbe.periodSeconds | int | `10` | Period seconds for livenessProbe |
| livenessProbe.successThreshold | int | `1` | Success threshold for livenessProbe |
| livenessProbe.timeoutSeconds | int | `1` | Timeout seconds for livenessProbe |
| mysql | object | `{"auth":{"existingSecret":"","rootPassword":""}}` | MySQL subchart by Bitnami. See https://artifacthub.io/packages/helm/bitnami/mysql?modal=values for all possible values |
| nameOverride | string | `""` | Name override for Valtimo-Backend |
| nodeSelector | object | `{}` | Node labels for Valtimo-backend pods assignment |
| persistence.annotations | object | `{}` |  |
| persistence.enabled | bool | `false` | Enable/disable persistent volumes for Valimo-backend |
| persistence.existingClaim | string | `nil` | persistence.existingClaim The name of an existing PVC to use for persistence |
| persistence.mountPath | string | `"/tmp"` | persistence.mountPath Path to mount the volume at. |
| persistence.size | string | `"1Gi"` | persistence.size Size of data volume |
| persistence.storageClass | string | `""` |  |
| podAnnotations | object | `{}` | Annotations for Valtimo-backend pods |
| podLabels | object | `{}` | Labels for Valtimo-backend pods |
| podSecurityContext.fsGroup | int | `2000` | Set Valtimo-backend's pod security fsGroup |
| postgresql | object | `{"auth":{"existingSecret":"","postgresPassword":"","secretKeys":{"adminPasswordKey":"","replicationPasswordKey":"","userPasswordKey":""}}}` | Postgresql subchart by Bitnami. See https://artifacthub.io/packages/helm/bitnami/postgresql?modal=values for all possible values |
| readinessProbe.failureThreshold | int | `6` | Failure threshold for readinessProbe |
| readinessProbe.initialDelaySeconds | int | `20` | Initial delay seconds for readinessProbe |
| readinessProbe.periodSeconds | int | `10` | Period seconds for readinessProbe |
| readinessProbe.successThreshold | int | `1` | Success threshold for readinessProbe |
| readinessProbe.timeoutSeconds | int | `1` | Timeout seconds for readinessProbe |
| replicaCount | int | `1` | Amount of replicas running the Valtimo-backend |
| resources | object | `{}` | Resources for Valtimo-backend |
| securityContext.capabilities.drop | list | `["ALL"]` | Valtimo-backend's container security context capabilities to be dropped |
| securityContext.readOnlyRootFilesystem | bool | `false` | Valtimo-backend's container security context readOnlyRootFilesystem |
| securityContext.runAsNonRoot | bool | `true` | Run Valtimo-backend containers as non-root |
| securityContext.runAsUser | int | `1000` | Run Valtimo-backend containers under this user-ID |
| service.port | int | `80` | Valtimo-backend service port |
| service.type | string | `"ClusterIP"` | Valtimo-backend service type |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | If not set and create is true, a name is generated using the fullname template |
| settings.camunda.adminUserID | string | `"admin"` | Default Camunda admin user |
| settings.camunda.adminUserPassword | string | `""` | Default Camunda admin password |
| settings.keycloak.authServerURL | string | `nil` | URL of Keycloak |
| settings.keycloak.clientID | string | `nil` | Client-ID to connect with Keycloak |
| settings.keycloak.clientSecret | string | `""` | Client-Secret to connect with Keycloak |
| settings.keycloak.publicKey | string | `nil` | Keycloak's Public Key used to verify signature of JWTs |
| settings.keycloak.realm | string | `nil` | Keycloak realm |
| settings.spring.actuator.password | string | `""` | Password to access the Spring actuator endpoint |
| settings.spring.actuator.username | string | `"admin"` | Username to access the Spring actuator endpoint |
| settings.spring.datasource.password | string | `""` | Password for the database |
| settings.spring.datasource.url | string | `nil` | URL for the database |
| settings.spring.datasource.username | string | `nil` | Username for the database |
| settings.spring.profiles.active | string | `"cloud"` | Activated Spring profiles |
| settings.valtimo.appHostName | string | `nil` | The hostname which exposes Valtimo-backend |
| settings.valtimo.connectorEncryptionSecret | string | `""` | Encryption secret |
| settings.valtimo.databaseType | string | `"postgres"` | Type of database to use (can by either 'postgres' or 'mysql') |
| settings.valtimo.serverPort | int | `8080` | The port on which Valtimo-backend is listening |
| tags.keycloak | bool | `true` | Deploy a Keycloak instance |
| tags.mysql | bool | `false` | Deploy a MySQL instance |
| tags.postgresql | bool | `true` | Deploy a PostgreSQL instance |
| tolerations | list | `[]` | Tolerations for Valtimo-backend pods assignment |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.12.0](https://github.com/norwoodj/helm-docs/releases/v1.12.0)
