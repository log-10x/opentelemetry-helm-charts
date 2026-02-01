# 10x + OpenTelemetry Helm Charts

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Release Status](https://github.com/log-10x/opentelemetry-helm-charts/actions/workflows/release.yaml/badge.svg?branch=main)](https://github.com/log-10x/opentelemetry-helm-charts/actions)

## Add the 10x + OpenTelemetry Helm repository

```sh
helm repo add log10x-open-telemetry https://log-10x.github.io/opentelemetry-helm-charts
```

You can then run `helm search repo log10x-open-telemetry` to see the charts.

### 10x + OpenTelemetry Collector

The chart can be used to install [OpenTelemetry Collector](https://github.com/open-telemetry/opentelemetry-collector) with the 10x Observability engine
in a Kubernetes cluster. More detailed documentation can be found in
[OpenTelemetry Collector chart directory](https://github.com/log-10x/opentelemetry-helm-charts/tree/main/charts/opentelemetry-collector).

## License

[Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0)
