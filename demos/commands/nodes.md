# Nodes

## Taints

Update the taints on one or more nodes.

  *  A taint consists of a key, value, and effect. As an argument here, it is expressed as key=value:effect.
  *  The key must begin with a letter or number, and may contain letters, numbers, hyphens, dots, and underscores, up to
253 characters.
  *  Optionally, the key can begin with a DNS subdomain prefix and a single '/', like example.com/my-app.
  *  The value is optional. If given, it must begin with a letter or number, and may contain letters, numbers, hyphens,
dots, and underscores, up to 63 characters.
  *  The effect must be NoSchedule, PreferNoSchedule or NoExecute.
  *  Currently taint can only apply to node.


### Usage:

```
kubectl taint NODE NAME KEY_1=VAL_1:TAINT_EFFECT_1 ... KEY_N=VAL_N:TAINT_EFFECT_N [options]
```

### Examples:

Update node 'foo' with a taint with key 'dedicated' and value 'special-user' and effect 'NoSchedule'
If a taint with that key and effect already exists, its value is replaced as specified
```
kubectl taint nodes foo dedicated=special-user:NoSchedule
```
 
Remove from node 'foo' the taint with key 'dedicated' and effect 'NoSchedule' if one exists
```
kubectl taint nodes foo dedicated:NoSchedule-
```

Remove from node 'foo' all the taints with key 'dedicated'
```
kubectl taint nodes foo dedicated-
```

Add a taint with key 'dedicated' on nodes having label mylabel=X
```
kubectl taint node -l myLabel=X  dedicated=foo:PreferNoSchedule
```

Add to node 'foo' a taint with key 'bar' and no value
```
kubectl taint nodes foo bar:NoSchedule
```

## Assigning Pods to Nodes | Node selector

first label node using:
```
k label node <node-name> <label-key>=<label-value>
```

then add nodeSelector in pod definition