# modem-stats

![Version: 3.0.1](https://img.shields.io/badge/Version-3.0.1-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square)

periodic cable modem data collection and save the results to InfluxDB

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/k8s-at-home/SB6183-stats-for-influxdb>
* <https://github.com/k8s-at-home/charts>

## Requirements

## Dependencies

| Repository | Name | Version |
|------------|------|---------|

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install modem-stats k8s-at-home/modem-stats
```

## Installing the Chart

To install the chart with the release name `modem-stats`

```console
helm install modem-stats k8s-at-home/modem-stats
```

## Uninstalling the Chart

To uninstall the `modem-stats` deployment

```console
helm uninstall modem-stats
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install modem-stats \
  --set env.TZ="America/New York" \
    k8s-at-home/modem-stats
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install modem-stats k8s-at-home/modem-stats -f values.yaml
```

## Custom configuration

![Screenshot](https://camo.githubusercontent.com/939e044c0491abf790d91bd1d7f909b187e4098c/68747470733a2f2f692e696d6775722e636f6d2f70705a6a6e6b502e706e67)

The configuration is set as a block of text through a configmap and mouted as a file in /src/config.ini Any value in this text block should match the defined sb6183 configuration. There are several values here that will have to match our kubernetes configuration.

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config.delay | int | `3600` | how many seconds to wait between checks |
| config.influxdb.database | string | `"cable_modem_stats"` | InfluxDB database |
| config.influxdb.host | string | `"influxdb-influxdb"` | InfluxDB hostname |
| config.influxdb.port | int | `8086` | InfluxDB port |
| config.influxdb.ssl | bool | `false` | InfluxDB connection using SSL |
| config.modem.url | string | `"http://192.168.100.1/RgConnect.asp"` | sb6183 stats URL page |
| debug | bool | `false` | Display debugging output |
| image.pullPolicy | string | `"IfNotPresent"` | modem-stats image pull policy |
| image.repository | string | `"billimek/sb6183-for-influxdb"` | modem-stats image |
| image.tag | string | `"latest"` | modem-stats image tag |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` | Key-value pairs to add as pod annotations |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |

## Changelog

All notable changes to this application Helm chart will be documented in this file but does not include changes from our common library. To read those click [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common#changelog).

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

### [3.0.1]

#### Added

- N/A

#### Changed

- N/A

#### Removed

- N/A

[3.0.1]: #3.0.1

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)