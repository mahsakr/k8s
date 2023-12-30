# Rollout

Manage the rollout of one or many resources.

 Valid resource types include:

* deployments
* daemonsets
* statefulsets

## Examples

Rollback to the previous deployment
```
kubectl rollout undo deployment/abc
```

Check the rollout status of a daemonset
```
kubectl rollout status daemonset/foo
```

Restart a deployment
```
kubectl rollout restart deployment/abc
```

Restart deployments with the app=nginx label
```
kubectl rollout restart deployment --selector=app=nginx
```

Available Commands:
*  history:       View rollout history
*  pause:         Mark the provided resource as paused
*  restart:       Restart a resource
*  resume:        Resume a paused resource
*  status:        Show the status of the rollout
*  undo:          Undo a previous rollout

## Usage

```
kubectl rollout SUBCOMMAND [options]
```

check the status of a rollout of a deployment
```
k rollout status deployment/m
```

check the status of a history rollout of a deployment
```
k rollout history deployment/m
```
