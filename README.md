# k8s

```
kind create cluster --config kind.yaml
```

```
istioctl install --set profile=minimal
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

```
k -n infra patch services apiserver -p '{"spec": {"externalIPs":["172.25.0.2"]}}'
```

```
$ grpcurl -plaintext -v 127.0.0.1:7777 list
grpc.reflection.v1alpha.ServerReflection
post.API
```
