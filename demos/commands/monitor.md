# Commands

## Metric Server

install metric server
```
git clone https://github.com/kodekloudhub/kubernetes-metrics-server.git
```

install
```
k apply -f . # make sure to move to the directory
``` 

try to get statistics
```
k top node

k top pod
```

Identify the POD that consumes the most Memory(bytes) in default namespace.
```
k top pod -n default
```


