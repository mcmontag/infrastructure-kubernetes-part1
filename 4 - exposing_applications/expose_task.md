### 1 - What do you see and what is happening after exposing via ClusterIP?

```
Sometimes the request is routed to the nginx container running on labeled-pod, which displays all of the output from
the bash command running in the html-content container within the same pod, while other times the request is routed
to the "vanilla" nginx app running on 'pod-nginx'.  Since we're exposing via ClusterIP, the service is only reachable
from within the cluster.  This is why we need to hit the proxy -- we're attempting to access the service from outside. 
```

### 2 - What is happening? How is the nodeport behaving different? Why?

```
The behavior of the actual service is the same -- sometimes it uses labeled-pod, sometimes it uses pod-nginx.  The
difference with NodePort is that we don't have to go through the proxy in order to reach the service, with the actual
port we listed as the nodePort being exposed (and mapped to port 80 of pods) on each node (in this case just the 
one minikube node, with two pods).  One thing I did notice is that it took quite a bit longer to get a different
pod (i.e. default index.html versus timestamps) when using NodePort.  Not really seeing anything in documentation
that would explain this, but did find it worth noting.
```
