# Command

# Namespace

create namespace
```
 k create ns dev
 or
 k create -f file 
 ```

explain type (replicaset , pod, .)
```
kubectl explain deployment
```

set default namespace
```
kubectl config set-context $(kubectl config current-context) --namespace=dev
```

get pods from all namespaces
```
k get pod --all-namespaces
or 
k get pod -A
```
