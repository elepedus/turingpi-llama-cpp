# TuringPi Llama.cpp Chart

Deploys [Llama.cpp server](https://github.com/ggerganov/llama.cpp/tree/master/examples/server) onto your TuringPi
cluster, complete with a persistent volume to store the model files, replication and an ingress. Assumes you have
followed the instructions at [docs.turingpi.com](https://docs.turingpi.com/docs/how-to-plan-kubernetes-installation) to
configure Longhorn, MetaLB and Traefik. By default, uses `lmstudio-ai/gemma-2b-it-GGUF` model, but this can be
overridden with custom values.

## Installation

```shell
helm install llama-cpp https://elepedus.github.io/turingpi-llama-cpp/turingpi-llama-cpp-0.0.1.tgz --namespace=llama-cpp
```

## Usage

By default, the ingress exposes the web UI at `llama.turingpi-cluster.local`, at the same IP address as you configured
for `turingpi-cluster.local` Make sure to update your `/etc/hosts` file so the new subdomain is accessible:

```
10.0.0.70 turing-cluster turing-cluster.local llama.turingpi-cluster llama.turingpi-cluster.local
```