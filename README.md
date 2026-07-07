# Log10x OpenTelemetry Helm Charts

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

> [!WARNING]
> **The forked `opentelemetry-collector` 10x chart is retired.**
>
> It wired a `log10x/edge-10x` sidecar to the Collector over **unix domain sockets**
> on a shared `/tmp` emptyDir (`/tmp/tenx-otel-in.sock` / `/tmp/tenx-otel-out.sock`).
>
> That fork is no longer used. The OpenTelemetry Collector now runs the 10x Engine as
> a `log10x/edge-10x` **sidecar container** added to the **official upstream**
> [`open-telemetry/opentelemetry-collector`](https://github.com/open-telemetry/opentelemetry-helm-charts)
> chart via a values overlay (`extraContainers`), talking over **loopback TCP**
> (OTLP/gRPC in, Fluent Forward back).
>
> **Use the current [Receiver deployment guide](https://doc.log10x.com/apps/receiver/deploy/) instead.**

The other charts in this repository (`opentelemetry-demo`, `opentelemetry-operator`,
`opentelemetry-kube-stack`, etc.) are plain upstream mirrors with no 10x integration.

## License

This repository is licensed under the [Apache License 2.0](LICENSE).

### Important: Log10x Product License Required

While the tooling itself is open source, **using Log10x requires a commercial license**.

| Component | License |
|-----------|---------|
| This repository (Helm charts) | Apache 2.0 (open source) |
| Log10x engine and runtime | Commercial license required |

**Get Started:**

- [Log10x Pricing](https://www.log10x.com/pricing?utm_source=github&utm_medium=readme&utm_campaign=opentelemetry-helm-charts&utm_content=footer)
- [Documentation](https://doc.log10x.com)
- [Contact Sales](mailto:sales@log10x.com)
