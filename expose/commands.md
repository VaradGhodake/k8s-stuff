## Example to expose svc (ClusterIP) or a pod/container

```sh
$ kubectl port-forward svc/svc-name -n namespace host_port:target_port
```
The service should be available at localhost:host_port. Intuitively, same thing can be done for pod/containers. Replace `svc` with `pod`. `target_port` should be chosen based on where the container is exposing it's service.
