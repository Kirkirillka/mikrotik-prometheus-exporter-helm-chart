# mikrotik-prometheus-exporter-helm-chart
Helm chart for https://github.com/nshttpd/mikrotik-exporter prometheus exporter

## Introduction

This chart creates a Mikrotik-Exporter deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

## Configuration

The following table lists the configurable parameters of the Mikrotik-Exporter chart and their default values.

|               Parameter                |                    Description                    |            Default            |
| -------------------------------------- | ------------------------------------------------- | ----------------------------- |
| `config`                               | Prometheus mikrotik configuration                 | {}                            |
| `secretConfig`                         | Whether to treat mikrotik configuration as secret | `false`                       |
| `configmapReload.name`                 | configmap-reload container name                   | `configmap-reload`            |
| `configmapReload.runAsUser`            | User to run configmap-reload container as         | `65534`                       |
| `configmapReload.runAsNonRoot`         | Run configmap-reload container as non-root        | `true`                        |
| `configmapReload.image.repository`     | configmap-reload container image repository       | `jimmidyson/configmap-reload` |
| `configmapReload.image.tag`            | configmap-reload container image tag              | `v0.2.2`                      |
| `configmapReload.image.pullPolicy`     | configmap-reload container image pull policy      | `IfNotPresent`                |
| `configmapReload.extraArgs`            | Additional configmap-reload container arguments   | `{}`                          |
| `configmapReload.extraConfigmapMounts` | Additional configmap-reload configMap mounts      | `[]`                          |
| `configmapReload.resources`            | configmap-reload pod resource requests & limits   | `{}`                          |
| `extraArgs`                            | Optional flags for mikrotik-exporter              | `[]`                          |
| `image.repository`                     | container image repository                        | `nshttpd/mikrotik-exporter`      |
| `image.tag`                            | container image tag                               | `1.0.9`                     |
| `image.pullPolicy`                     | container image pull policy                       | `IfNotPresent`                |
| `image.pullSecrets`                    | container image pull secrets                      | `[]`                          |
| `ingress.annotations`                  | Ingress annotations                               | None                          |
| `ingress.enabled`                      | Enables Ingress                                   | `false`                       |
| `ingress.hosts`                        | Ingress accepted hostnames                        | None                          |
| `ingress.tls`                          | Ingress TLS configuration                         | None                          |
| `nodeSelector`                         | node labels for pod assignment                    | `{}`                          |
| `runAsUser`                            | User to run mikrotik-exporter container as        | `1000`                        |
| `readOnlyRootFilesystem`               | Set mikrotik-exporter file-system to read-only    | `true`                        |
| `runAsNonRoot`                         | Run mikrotik-exporter as non-root                 | `true`                        |
| `tolerations`                          | node tolerations for pod assignment               | `[]`                          |
| `affinity`                             | node affinity for pod assignment                  | `{}`                          |
| `podAnnotations`                       | annotations to add to each pod                    | `{}`                          |
| `resources`                            | pod resource requests & limits                    | `{}`                          |
| `restartPolicy`                        | container restart policy                          | `Always`                      |
| `service.annotations`                  | annotations for the service                       | `{}`                          |
| `service.labels`                       | additional labels for the service                 | None                          |
| `service.type`                         | type of service to create                         | `ClusterIP`                   |
| `service.port`                         | port for the mikrotik http service                | `9436`                        |
| `service.externalIPs`                  | list of external ips                              | []                            |
