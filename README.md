# K8s sample resources

Some sample Kubernetes resource definitions to get you started quickly for some experimentation in Kubernetes.

All resource definitions have short URLs that you can type directly on the command line.

## Resources

- **Deployment** — a Deployment running three NGINX Pods
- **Service** — a Service exposing the Pods of the above Deployment
- **Pod** — a Pod running NGINX
- **Jump Pod** — a Pod to "exec" into (see [below](#jump-pod-instructions))

## URLs

### Short URLs

> <https://bit.ly/k8s-sample-deployment><br />
<https://bit.ly/k8s-sample-service><br />
<https://bit.ly/k8s-sample-pod><br />
<https://bit.ly/k8s-sample-jump-pod>

### Long URLs

> <https://raw.githubusercontent.com/weibeld/k8s-sample-resources/master/deployment.yaml><br />
<https://raw.githubusercontent.com/weibeld/k8s-sample-resources/master/service.yaml><br />
<https://raw.githubusercontent.com/weibeld/k8s-sample-resources/master/pod.yaml><br />
<https://raw.githubusercontent.com/weibeld/k8s-sample-resources/master/jump-pod.yaml>

## Usage

Create resource in Kubernetes:

```bash
kubectl apply -f <url>
```

Download resource definiton:

```bash
curl -L <url>
```

## Examples

Create a Deployment:

```bash
kubectl apply -f https://bit.ly/k8s-sample-deployment
```

Download the Pod resource definition for local editing:

```bash
curl -L https://bit.ly/k8s-sample-pod >my-pod.yaml
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

The container image of the Pod is [weibeld/ubuntu-networking](https://github.com/weibeld/docker-ubuntu-networking). This is Ubuntu with many networking tools installed. So, you can use `curl` , `dig`, etc. right away.
