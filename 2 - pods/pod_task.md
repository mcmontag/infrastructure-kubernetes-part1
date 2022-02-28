### 1 - Enter command for creation of pod_1.yml

```
kubectl create -f manifests/pod_1.yml
```

### 2 - Enter command used to verify the pod_1.yml (describe or proxy with url)

```
kubectl describe pod pod-nginx
```

### 3 - Describe how the containers are working together after applying pod_2.yml

```
The containers share a the pod-level volume named html-content.  The bash script running in container 'pod-content' writes
out to the same file (index.html) that nginx (running in container pod-nginx) reads from (and serves on port 80).
