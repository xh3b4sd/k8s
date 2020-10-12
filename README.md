# k8s

```
kind create cluster --config kind.yaml
```

```
helm -n infra install infra ./infra/ --create-namespace
```


```
helm -n infra install apiserver ./apiserver/
```


```
helm -n infra install envoy ./envoy/
```


```
k -n infra patch services envoy -p '{"spec": {"type": "LoadBalancer", "externalIPs":["172.25.0.2"]}}'
```
