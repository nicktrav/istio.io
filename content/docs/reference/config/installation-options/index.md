---
title: Installation Options
description: Describes the options available when installing Istio using the included Helm chart.
weight: 30
keywords: [kubernetes,helm]
---

To customize Istio install using Helm, use the `--set <key>=<value>` option in Helm command to override one or more values. The set of supported keys is shown in the table below.

<!-- Run python scripts/tablegen.py to generate this table -->
<!-- AUTO-GENERATED-START -->
## `certmanager` options

| Key | Default Value | Description |
| --- | --- | --- |
| `certmanager.enabled` | `true` |  |
| `certmanager.hub` | `quay.io/jetstack` |  |
| `certmanager.tag` | `v0.3.1` |  |
| `certmanager.resources` | `{}` |  |

## `galley` options

| Key | Default Value | Description |
| --- | --- | --- |
| `galley.enabled` | `true` |  |
| `galley.replicaCount` | `1` |  |
| `galley.image` | `galley` |  |

## `gateways` options

| Key | Default Value | Description |
| --- | --- | --- |
| `gateways.enabled` | `true` |  |
| `gateways.istio-ingressgateway.enabled` | `true` |  |
| `gateways.istio-ingressgateway.labels.app` | `istio-ingressgateway` |  |
| `gateways.istio-ingressgateway.labels.istio` | `ingressgateway` |  |
| `gateways.istio-ingressgateway.replicaCount` | `1` |  |
| `gateways.istio-ingressgateway.autoscaleMin` | `1` |  |
| `gateways.istio-ingressgateway.autoscaleMax` | `5` |  |
| `gateways.istio-ingressgateway.resources` | `{}` |  |
| `gateways.istio-ingressgateway.loadBalancerIP` | `""` |  |
| `gateways.istio-ingressgateway.externalIPs` | [] |  |
| `gateways.istio-ingressgateway.serviceAnnotations` | `{}` |  |
| `gateways.istio-ingressgateway.type` | `LoadBalancer #change to NodePort, ClusterIP or LoadBalancer if need be` |  |
| `gateways.istio-ingressgateway.ports.targetPort` | `80` |  |
| `gateways.istio-ingressgateway.ports.name` | `http2` |  |
| `gateways.istio-ingressgateway.ports.nodePort` | `31380` |  |
| `gateways.istio-ingressgateway.ports.name` | `https` |  |
| `gateways.istio-ingressgateway.ports.nodePort` | `31390` |  |
| `gateways.istio-ingressgateway.ports.name` | `tcp` |  |
| `gateways.istio-ingressgateway.ports.nodePort` | `31400` |  |
| `gateways.istio-ingressgateway.ports.targetPort` | `15011` |  |
| `gateways.istio-ingressgateway.ports.name` | `tcp-pilot-grpc-tls` |  |
| `gateways.istio-ingressgateway.ports.targetPort` | `8060` |  |
| `gateways.istio-ingressgateway.ports.name` | `tcp-citadel-grpc-tls` |  |
| `gateways.istio-ingressgateway.ports.targetPort` | `15030` |  |
| `gateways.istio-ingressgateway.ports.name` | `http2-prometheus` |  |
| `gateways.istio-ingressgateway.ports.targetPort` | `15031` |  |
| `gateways.istio-ingressgateway.ports.name` | `http2-grafana` |  |
| `gateways.istio-ingressgateway.secretVolumes.secretName` | `istio-ingressgateway-certs` |  |
| `gateways.istio-ingressgateway.secretVolumes.mountPath` | `/etc/istio/ingressgateway-certs` |  |
| `gateways.istio-ingressgateway.secretVolumes.secretName` | `istio-ingressgateway-ca-certs` |  |
| `gateways.istio-ingressgateway.secretVolumes.mountPath` | `/etc/istio/ingressgateway-ca-certs` |  |
| `gateways.istio-egressgateway.enabled` | `true` |  |
| `gateways.istio-egressgateway.labels.app` | `istio-egressgateway` |  |
| `gateways.istio-egressgateway.labels.istio` | `egressgateway` |  |
| `gateways.istio-egressgateway.replicaCount` | `1` |  |
| `gateways.istio-egressgateway.autoscaleMin` | `1` |  |
| `gateways.istio-egressgateway.autoscaleMax` | `5` |  |
| `gateways.istio-egressgateway.serviceAnnotations` | `{}` |  |
| `gateways.istio-egressgateway.type` | `ClusterIP #change to NodePort or LoadBalancer if need be` |  |
| `gateways.istio-egressgateway.ports.name` | `http2` |  |
| `gateways.istio-egressgateway.ports.name.name` | `https` |  |
| `gateways.istio-egressgateway.secretVolumes.secretName` | `istio-egressgateway-certs` |  |
| `gateways.istio-egressgateway.secretVolumes.secretName.mountPath` | `/etc/istio/egressgateway-certs` |  |
| `gateways.istio-egressgateway.secretVolumes.secretName.secretName` | `istio-egressgateway-ca-certs` |  |
| `gateways.istio-egressgateway.secretVolumes.secretName.mountPath` | `/etc/istio/egressgateway-ca-certs` |  |
| `gateways.istio-ilbgateway.enabled` | `false` |  |
| `gateways.istio-ilbgateway.enabled.labels.app` | `istio-ilbgateway` |  |
| `gateways.istio-ilbgateway.enabled.labels.istio` | `ilbgateway` |  |
| `gateways.istio-ilbgateway.enabled.replicaCount` | `1` |  |
| `gateways.istio-ilbgateway.enabled.autoscaleMin` | `1` |  |
| `gateways.istio-ilbgateway.enabled.autoscaleMax` | `5` |  |
| `gateways.istio-ilbgateway.enabled.resources.requests.cpu` | `800m` |  |
| `gateways.istio-ilbgateway.enabled.resources.requests.memory` | `512Mi` |  |
| `gateways.istio-ilbgateway.enabled.loadBalancerIP` | `""` |  |
| `gateways.istio-ilbgateway.enabled.serviceAnnotations.cloud.google.com/load-balancer-type` | `"internal"` |  |
| `gateways.istio-ilbgateway.enabled.type` | `LoadBalancer` |  |
| `gateways.istio-ilbgateway.enabled.ports.name` | `grpc-pilot-mtls` |  |
| `gateways.istio-ilbgateway.enabled.ports.name` | `grpc-pilot` |  |
| `gateways.istio-ilbgateway.enabled.ports.targetPort` | `8060` |  |
| `gateways.istio-ilbgateway.enabled.ports.name` | `tcp-citadel-grpc-tls` |  |
| `gateways.istio-ilbgateway.enabled.ports.name` | `tcp-dns` |  |
| `gateways.istio-ilbgateway.enabled.secretVolumes.secretName` | `istio-ilbgateway-certs` |  |
| `gateways.istio-ilbgateway.enabled.secretVolumes.mountPath` | `/etc/istio/ilbgateway-certs` |  |
| `gateways.istio-ilbgateway.enabled.secretVolumes.secretName` | `istio-ilbgateway-ca-certs` |  |
| `gateways.istio-ilbgateway.enabled.secretVolumes.mountPath` | `/etc/istio/ilbgateway-ca-certs` |  |

## `global` options

| Key | Default Value | Description |
| --- | --- | --- |
| `global.hub` | `docker.io/istio` |  |
| `global.tag` | `1.0.0` |  |
| `global.k8sIngressSelector` | `ingress` |  |
| `global.k8sIngressHttps` | `false` |  |
| `global.proxy.image` | `proxyv2` |  |
| `global.proxy.resources.requests.cpu` | `10m` |  |
| `global.proxy.accessLogFile` | `"/dev/stdout"` |  |
| `global.proxy.enableCoreDump` | `false` |  |
| `global.proxy.includeIPRanges` | `"*"` |  |
| `global.proxy.excludeIPRanges` | `""` |  |
| `global.proxy.includeInboundPorts` | `"*"` |  |
| `global.proxy.excludeInboundPorts` | `""` |  |
| `global.proxy.autoInject` | `enabled` |  |
| `global.proxy.envoyStatsd.enabled` | `true` |  |
| `global.proxy.envoyStatsd.host` | `istio-statsd-prom-bridge` |  |
| `global.proxy.envoyStatsd.port` | `9125` |  |
| `global.proxy_init.image` | `proxy_init` |  |
| `global.imagePullPolicy` | `IfNotPresent` |  |
| `global.controlPlaneSecurityEnabled` | `true` |  |
| `global.disablePolicyChecks` | `false` |  |
| `global.enableTracing` | `true` |  |
| `global.mtls.enabled` | `true` |  |
| `global.arch.amd64` | `2` |  |
| `global.arch.s390x` | `2` |  |
| `global.arch.ppc64le` | `2` |  |
| `global.oneNamespace` | `false` |  |
| `global.configValidation` | `true` |  |
| `global.meshExpansion` | `false` |  |
| `global.meshExpansionILB` | `false` |  |
| `global.defaultResources.requests.cpu` | `10m` |  |
| `global.hyperkube.hub` | `quay.io/coreos` |  |
| `global.hyperkube.tag` | `v1.7.6_coreos.0` |  |
| `global.priorityClassName` | `""` |  |
| `global.crds` | `true` |  |

## `grafana` options

| Key | Default Value | Description |
| --- | --- | --- |
| `grafana.enabled` | `true` |  |
| `grafana.replicaCount` | `1` |  |
| `grafana.image` | `grafana` |  |
| `grafana.security.enabled` | `true` |  |
| `grafana.security.adminUser` | `admin` |  |
| `grafana.security.adminPassword` | `admin` |  |
| `grafana.service.annotations` | `{}` |  |
| `grafana.service.name` | `http` |  |
| `grafana.service.type` | `ClusterIP` |  |
| `grafana.service.externalPort` | `3000` |  |
| `grafana.service.internalPort` | `3000` |  |

## `ingress` options

| Key | Default Value | Description |
| --- | --- | --- |
| `ingress.enabled` | `true` |  |
| `ingress.replicaCount` | `1` |  |
| `ingress.autoscaleMin` | `1` |  |
| `ingress.autoscaleMax` | `5` |  |
| `ingress.service.annotations` | `{}` |  |
| `ingress.service.loadBalancerIP` | `""` |  |
| `ingress.service.type` | `LoadBalancer #change to NodePort, ClusterIP or LoadBalancer if need be` |  |
| `ingress.service.ports.name` | `http` |  |
| `ingress.service.ports.nodePort` | `32000` |  |
| `ingress.service.ports.name` | `https` |  |
| `ingress.service.selector.istio` | `ingress` |  |

## `kiali` options

| Key | Default Value | Description |
| --- | --- | --- |
| `kiali.enabled` | `false` | Note that if using the demo or demo-auth yaml when installing via Helm, this default will be `true`. |
| `kiali.replicaCount` | `1` |  |
| `kiali.hub` | `docker.io/kiali` |  |
| `kiali.tag` | `v0.12` |  |
| `kiali.ingress.enabled` | `false` |  |
| `kiali.contextPath` | `/kiali` | The root context path to access the Kiali UI. |
| `kiali.dashboard.secretName` | `kiali` | You must create a secret with this name - one is not provided out-of-box.  |
| `kiali.dashboard.usernameKey` | `username` | This is the key name within the secret whose value is the actual username. |
| `kiali.dashboard.passphraseKey` | `passphrase` | This is the key name within the secret whose value is the actual passphrase. |
| `kiali.dashboard.jaegerURL` | | If you have Jaeger installed and it is accessible to client browsers, then set this property to its external URL. Kiali will redirect users to this URL when Jaeger tracing is to be shown. |
| `kiali.dashboard.grafanaURL` | | If you have Grafana installed and it is accessible to client browsers, then set this property to its external URL. Kiali will redirect users to this URL when Grafana metrics are to be shown. |

## `mixer` options

| Key | Default Value | Description |
| --- | --- | --- |
| `mixer.enabled` | `true` |  |
| `mixer.replicaCount` | `1` |  |
| `mixer.autoscaleMin` | `1` |  |
| `mixer.autoscaleMax` | `5` |  |
| `mixer.image` | `mixer` |  |
| `mixer.istio-policy.autoscaleEnabled` | `true` |  |
| `mixer.istio-policy.autoscaleMin` | `1` |  |
| `mixer.istio-policy.autoscaleMax` | `5` |  |
| `mixer.istio-policy.cpu.targetAverageUtilization` | `80` |  |
| `mixer.istio-telemetry.autoscaleEnabled` | `true` |  |
| `mixer.istio-telemetry.autoscaleMin` | `1` |  |
| `mixer.istio-telemetry.autoscaleMax` | `5` |  |
| `mixer.istio-telemetry.cpu.targetAverageUtilization` | `80` |  |
| `mixer.prometheusStatsdExporter.hub` | `docker.io/prom` |  |
| `mixer.prometheusStatsdExporter.tag` | `v0.6.0` |  |

## `pilot` options

| Key | Default Value | Description |
| --- | --- | --- |
| `pilot.enabled` | `true` |  |
| `pilot.replicaCount` | `1` |  |
| `pilot.autoscaleMin` | `1` |  |
| `pilot.autoscaleMax` | `1` |  |
| `pilot.image` | `pilot` |  |
| `pilot.sidecar` | `true` |  |
| `pilot.traceSampling` | `100.0` |  |
| `pilot.resources.requests.cpu` | `500m` |  |
| `pilot.resources.requests.memory` | `2048Mi` |  |

## `prometheus` options

| Key | Default Value | Description |
| --- | --- | --- |
| `prometheus.enabled` | `true` |  |
| `prometheus.replicaCount` | `1` |  |
| `prometheus.hub` | `docker.io/prom` |  |
| `prometheus.tag` | `v2.3.1` |  |
| `prometheus.service.annotations` | `{}` |  |
| `prometheus.service.nodePort.enabled` | `false` |  |
| `prometheus.service.nodePort.port` | `32090` |  |

## `security` options

| Key | Default Value | Description |
| --- | --- | --- |
| `security.replicaCount` | `1` |  |
| `security.image` | `citadel` |  |
| `security.selfSigned` | `true # indicate if self-signed CA is used.` |  |

## `sidecarInjectorWebhook` options

| Key | Default Value | Description |
| --- | --- | --- |
| `sidecarInjectorWebhook.enabled` | `true` |  |
| `sidecarInjectorWebhook.replicaCount` | `1` |  |
| `sidecarInjectorWebhook.image` | `sidecar_injector` |  |
| `sidecarInjectorWebhook.enableNamespacesByDefault` | `false` |  |

## `telemetry-gateway` options

| Key | Default Value | Description |
| --- | --- | --- |
| `telemetry-gateway.gatewayName` | `ingressgateway` |  |
| `telemetry-gateway.grafanaEnabled` | `true` |  |
| `telemetry-gateway.prometheusEnabled` | `true` |  |

## `tracing` options

| Key | Default Value | Description |
| --- | --- | --- |
| `tracing.enabled` | `true` |  |
| `tracing.provider` | `jaeger` |  |
| `tracing.jaeger.hub` | `docker.io/jaegertracing` |  |
| `tracing.jaeger.tag` | `1.5` |  |
| `tracing.jaeger.memory.max_traces` | `50000` |  |
| `tracing.jaeger.ui.port` | `16686` |  |
| `tracing.replicaCount` | `1` |  |
| `tracing.service.annotations` | `{}` |  |
| `tracing.service.name` | `http` |  |
| `tracing.service.type` | `ClusterIP` |  |
| `tracing.service.externalPort` | `9411` |  |
| `tracing.service.internalPort` | `9411` |  |
| `tracing.ingress.enabled` | `false` |  |

<!-- AUTO-GENERATED-END -->








