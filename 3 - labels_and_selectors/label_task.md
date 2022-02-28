
### 1 - What is the command used to add labels to the pod

```
kubectl label pods labeled-pod app_name=nginx env=dev
```


### 2 - What is the command used to remove labels from the pod

```
kubectl label pods labeled-pod app_name- env-
```

### 3 - What is the command used to select pods using labels with equality

```
kubectl get pods -l app_name==nginx
```

### 4 - What is the command used to select pods using the set selector

```
kubectl get pods -l "app_name in (nginx),env notin (prod)"
```
