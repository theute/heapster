# Heapster

[![GoDoc](https://godoc.org/k8s.io/heapster?status.svg)](https://godoc.org/k8s.io/heapster) [![Build Status](https://travis-ci.org/kubernetes/heapster.svg?branch=master)](https://travis-ci.org/kubernetes/heapster)

Heapster enables Container Cluster Monitoring and Performance Analysis.

Heapster currently supports [Kubernetes](https://github.com/kubernetes/kubernetes) and CoreOS natively.
It can be extended to support other cluster management solutions easily.
Heapster collects and interprets various signals like compute resource usage, lifecycle events, etc, and exports cluster metrics via [REST endpoints](docs/model.md).
**Note: Some of the endpoints are only valid in Kubernetes clusters**

Use [Kubedash](https://github.com/kubernetes/kubedash) to visualize data exported by Heapster.

Heapster supports multiple sources of data.
More information [here](docs/source-configuration.md).

Heapster supports a pluggable storage backend.
It supports [InfluxDB](http://influxdb.com) with [Grafana](http://grafana.org/docs/features/influxdb), [Google Cloud Monitoring](https://cloud.google.com/monitoring/), [Google Cloud Logging](https://cloud.google.com/logging/) and [Hawkular](http://www.hawkular.org).
We welcome patches that add additional storage backends.
Documentation on storage sinks [here](docs/sink-configuration.md)
The current version of Storage Schema is documented [here](docs/storage-schema.md).

### Running Heapster on Kubernetes

To run Heapster on a Kubernetes cluster with,
- InfluxDB use [this guide](docs/influxdb.md).
- Google Cloud Monitoring and Google Cloud Logging use [this guide](docs/google.md).

### Running Heapster on OpenShift

Using Heapster to monitor an OpenShift cluster requires some additional changes to the Kubernetes instructions to allow communication between the Heapster instance and OpenShift's secured endpoints. To run a combination of Heapster and Hawkular-Metrics, follow [this guide](https://github.com/openshift/origin-metrics/blob/master/README.md).

### Running Heapster on CoreOS

Heapster communicates with the local fleet server to get cluster information. It expected cAdvisor to be running on all the nodes. Refer to [this guide](docs/coreos.md).

### Running in other cluster management systems.

Heapster can be used to enable cluster-wide monitoring on other cluster management solutions by running a simple cluster-specific buddy container that will help Heapster with discovery of hosts.

### Running in standalone mode.

It is also possible to run Heapster standalone on a host with cAdvisor using [this guide](docs/standalone.md).

#### Troubleshooting guide [here](docs/debugging.md)

### Community

Contributions, questions, and comments are all welcomed and encouraged! Heapster and cAdvisor developers hang out in the [#google-containers](http://webchat.freenode.net/?channels=google-containers) room on freenode.net.  You can also reach us on the [google-containers Google Groups mailing list](https://groups.google.com/forum/#!forum/google-containers).
