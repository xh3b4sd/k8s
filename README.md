# k8s

```
kind create cluster --config kind.yaml
```

TODO with Docker for Mac increase container memory.

```
istioctl install -f istio.yaml
```

```
k create namespace infra
k label namespace infra istio-injection=enabled
```

```
helm -n infra install infra ./infra/
```

```
helm -n infra install apiserver ./apiserver/
```

TODO check logs for all pods.

```
k -n infra logs -f apiserver-xxxxxxxxxx-xxxxx apiserver
```

```
$ while :; do grpcurl -plaintext 127.0.0.1:7777 post.API/Search; sleep 1; done
{
  "message": "search output"
}
```
