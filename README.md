# Log10x OpenTelemetry Helm Charts

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

This repository contains [Helm](https://helm.sh/) charts for OpenTelemetry with integrated [Log10x](https://log10x.com) sidecar support.

**Forked from:** [open-telemetry/opentelemetry-helm-charts](https://github.com/open-telemetry/opentelemetry-helm-charts)

## Usage

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repo as follows:

```console
helm repo add log10x-otel https://log-10x.github.io/otel-helm-charts
```

## Helm Charts

You can then run `helm search repo log10x-otel` to see the charts.

### OpenTelemetry Collector (Log10x Enhanced)

The chart can be used to install [OpenTelemetry Collector](https://github.com/open-telemetry/opentelemetry-collector)
with optional Log10x sidecar integration for log cost analytics and optimization.

```bash
helm install my-collector log10x-otel/log10x-otel-collector -f values.yaml
```

## Log10x Integration

Enable Log10x by setting `tenx.enabled: true` in your values file:

```yaml
tenx:
  enabled: true
  apiKey: "YOUR-LICENSE-KEY"
  kind: "regulate"  # Options: report, regulate, optimize
  runtimeName: "my-otel-collector"

  # Optional: GitOps configuration
  github:
    config:
      enabled: true
      token: "YOUR-GITHUB-TOKEN"
      repo: "YOUR-ORG/YOUR-CONFIG-REPO"
```

### Log10x Modes

| Mode | Description |
|------|-------------|
| `report` | Analytics-only mode - generates cost and usage metrics without modifying logs |
| `regulate` | Filtering mode - reduces log volume based on configured rules |
| `optimize` | Full optimization - reduces log volume while preserving information |

## Documentation

- [Log10x Documentation](https://doc.log10x.com)
- [Edge Reporter Deployment](https://doc.log10x.com/apps/edge/reporter/deploy/)
- [Edge Regulator Deployment](https://doc.log10x.com/apps/edge/regulator/deploy/)
- [Edge Optimizer Deployment](https://doc.log10x.com/apps/edge/optimizer/deploy/)

## Upstream Charts

This repository also includes the following charts from the upstream OpenTelemetry project:

- OpenTelemetry Demo
- OpenTelemetry Operator
- OpenTelemetry eBPF Instrumentation

## License

[Apache 2.0 License](./LICENSE).

## Credits

Based on the official [OpenTelemetry Helm Charts](https://github.com/open-telemetry/opentelemetry-helm-charts).
