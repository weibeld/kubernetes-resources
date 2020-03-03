# Kubernetes sample resources

Some sample Kubernetes resource definitions that are directly accessible through URLs.

## Example usage

Create a Deployment, a Service exposing it, and a "jump" Pod:

```bash
kubectl apply -f https://bit.ly/k8s-sample-deployment
kubectl apply -f https://bit.ly/k8s-sample-service
kubectl apply -f https://bit.ly/k8s-sample-jump-pod
```

## Provided resource definitions

- **[Deployment](deployment.yaml):** a Deployment running three NGINX Pods
- **[Service](service.yaml):** a Service (ClusterIP) exposing the Pods of the above Deployment
- **[Headless Service](headless-service.yaml):** a headless Service exposing the Pods of the above Deployment
- **[Pod](pod.yaml):** a single Pod running NGINX
- **[Jump Pod](jump-pod.yaml):** a single Pod intended for "exec"ing ([see below](#jump-pod-instructions))

## URLs

### Short URLs

> <https://bit.ly/k8s-sample-deployment><br />
<https://bit.ly/k8s-sample-service><br />
<https://bit.ly/k8s-sample-headless-service><br />
<https://bit.ly/k8s-sample-pod><br />
<https://bit.ly/k8s-sample-jump-pod>

### Long URLs

> <https://raw.githubusercontent.com/weibeld/k8s-sample-resources/master/deployment.yaml><br />
<https://raw.githubusercontent.com/weibeld/k8s-sample-resources/master/service.yaml><br />
<https://raw.githubusercontent.com/weibeld/k8s-sample-resources/master/headless-service.yaml><br />
<https://raw.githubusercontent.com/weibeld/k8s-sample-resources/master/pod.yaml><br />
<https://raw.githubusercontent.com/weibeld/k8s-sample-resources/master/jump-pod.yaml>

## General usage

Directly apply a resource definition:

```bash
kubectl apply -f <url>
```

Download a resource definiton:

```bash
curl -L <url>
```

## Jump Pod instructions

Create the jump Pod with:

```bash
kubectl apply -f https://bit.ly/k8s-sample-jump-pod
```

When the Pod is running, "exec" into it with:

```bash
kubectl exec -ti jump-pod bash
```

The Pod runs a [weibeld/ubuntu-networking](https://github.com/weibeld/docker-ubuntu-networking) container, which is Ubuntu 18.04 with some common networking tools installed.
