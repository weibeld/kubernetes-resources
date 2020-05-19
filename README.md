# Kubernetes sample resources

Some sample Kubernetes resource definitions accessibel through short URLs.

## Example usage

Create an NGINX Deployment, a Service exposing the Deployment, and a jump Pod:

```bash
kubectl apply -f https://bit.ly/deployment-nginx
kubectl apply -f https://bit.ly/service-deployment-nginx
kubectl apply -f https://bit.ly/jump-pod
```

## Resource definitions

### Deployments

- [`deployment-nginx.yaml`](deployment-nginx.yaml): Deployment with 3 replicas of [NGINX](https://hub.docker.com/_/nginx) Pods with an `app=deployment-nginx` label
    - <https://bit.ly/deployment-nginx>
- [`deployment-alpine.yaml`](deployment-alpine.yaml): Deployment with 3 replicas of [Alpine](https://hub.docker.com/_/alpine) Pods with an `app=deployment-alpine` label
    - <https://bit.ly/deployment-alpine>

### DaemonSets

- [`daemonset-nginx.yaml`](daemonset-nginx.yaml): DaemonSet of [NGINX](https://hub.docker.com/_/nginx) Pods with an `app=daemonset-nginx` label
    - <https://bit.ly/daemonset-nginx>
- [`daemonset-alpine.yaml`](deployment-alpine.yaml): DaemonSet of [Alpine](https://hub.docker.com/_/alpine) Pods with an `app=daemonset-alpine` label
    - <https://bit.ly/daemonset-alpine>

### Services 

- [`service-deployment-nginx.yaml`](service-deployment-nginx.yaml): Service exposing Pods with an `app=deployment-nginx` label on port 80
    - <https://bit.ly/service-deployment-nginx>
- [`service-deployment-nginx-headless.yaml`](service-deployment-nginx-headless.yaml): Headless Service exposing Pods with an `app=deployment-nginx` label on port 80
    - <https://bit.ly/service-deployment-nginx-headless>
- [`service-daemonset-nginx.yaml`](service-daemonset-nginx.yaml): Service exposing Pods with an `app=daemonset-nginx` label on port 80
    - <https://bit.ly/service-daemonset-nginx>
- [`service-daemonset-nginx-headless.yaml`](service-daemonset-nginx-headless.yaml): Headless Service exposing Pods with an `app=daemonset-nginx` label on port 80
    - <https://bit.ly/service-daemonset-nginx-headless>

### Jump Pods

- [`jump-pod.yaml`](jump-pod.yaml): jump Pod running the [`weibeld/ubuntu-networking`](https://hub.docker.com/repository/docker/weibeld/ubuntu-networking) container image
    - <https://bit.ly/jump-pod>
- [`jump-pod-host-network.yaml`](jump-pod-host-network.yaml): jump Pod in the host network running the [`weibeld/ubuntu-networking`](https://hub.docker.com/repository/docker/weibeld/ubuntu-networking) container image
    - <https://bit.ly/jump-pod-host-network>

## General usage

Directly apply a resource definition:

```bash
kubectl apply -f <url>
```

Download a resource definition:

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
