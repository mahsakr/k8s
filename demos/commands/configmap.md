# Commands

## ConfigMap

Aliases:
configmap, cm

create a configmap
```
k create configmap
```

Create a new config map named my-config based on folder bar
```
kubectl create configmap my-config --from-file=path/to/bar
```

Create a new config map named my-config with specified keys instead of file basenames on disk
```
kubectl create configmap my-config --from-file=key1=/path/to/bar/file1.txt --from-file=key2=/path/to/bar/file2.txt
```

Create a new config map named my-config with key1=config1 and key2=config2
```
kubectl create configmap my-config --from-literal=key1=config1 --from-literal=key2=config2
```

Create a new config map named my-config from the key=value pairs in the file
```
kubectl create configmap my-config --from-file=path/to/bar
```

Create a new config map named my-config from an env file
```
kubectl create configmap my-config --from-env-file=path/to/foo.env --from-env-file=path/to/bar.env
```


