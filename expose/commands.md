# Example to expose svc (ClusterIP) or a pod/container

1. Find the `target_port`

```sh
# list all the pods
$ kubectl get pods -n namespace -o wide

# more info to find the port, similar command for svc
$ kubectl describe pods pod_name -n namespace
```

2. Expose for development and troubleshooting

```sh
$ kubectl port-forward svc/svc-name -n namespace host_port:target_port
```
The service should be available at localhost:host_port. Intuitively, same thing can be done for pod/containers. Replace `svc` with `pod`. `target_port` should be chosen based on where the container is exposing it's service.
