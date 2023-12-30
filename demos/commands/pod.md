# Commands

## Pod
create pod without file from image
```
kubectl run <podname> --image=<imagename>
```

create pod with file
```
kubectl create -f <pod-definition.yml>
```

Create an NGINX Pod
```
kubectl run nginx --image=nginx
```

Generate POD Manifest YAML file (-o yaml). Don't create it(--dry-run)
```
kubectl run redis --image=redis123 --dry-run=client -o yaml
```

Create a new pod called custom-nginx using the nginx image and expose it on container port 8080
```
 k run custom-nginx --image=nginx --port=8080
```


create pod with dry run and save output in yaml
```
kubectl run redis --image=redis123 --dry-run=client -o yaml > redis.yml
```

extract the definition of an existing pod/object to a file 
```
kubectl get pod <pod-name> -o yaml > pod-definition.yaml
```

to update pods/objects by apply changes to the yaml files 
```
kubectl apply -f redis.yml
```

display more ( like node and ip)
```
kubectl get pod -o wide
```

get with namespace
```
 k get pod --namespace=dev
 or
 k get pod -n=dev
 ```

get from all namespace
```
 k get pod --all-namespaces
 or
 k get pod -A
 or 
 k get -A | grep <text>
 ```


describe pod
```
kubectl describe pod podname
```

delete pod
```
kubectl delete pod podname
```


Create a pod with the given specifications. By default it displays a blue background. Set the given command line arguments to change it to green.

Pod Name: webapp-green
Image: kodekloud/webapp-color
Command line arguments: --color=green

```
k run webapp-green4 --image=kodekloud/webapp-color -- --color green
```

## Labels and selectors

select by label:
```
k get pod --selector env=dev
```

select matching many labels
```
k get pod --selector env=prod,bu=finance,tier=frontend
```

## Edit a POD
Remember, you CANNOT edit specifications of an existing POD other than the below:
```
spec.containers[*].image

spec.initContainers[*].image

spec.activeDeadlineSeconds

spec.tolerations
```

one of the options to edit a pod is to extract the pod definition in YAML format to a file using the command
```
kubectl get pod webapp -o yaml > my-new-pod.yaml
```

Then make the changes to the exported file using an editor (vi editor). Save the changes
```
vi my-new-pod.yaml
```

Then delete the existing pod
```
kubectl delete pod webapp
```

Then create a new pod with the edited file
```
kubectl create -f my-new-pod.yaml
```

## Environment Variable

## Security Contexts

## Resource requirements

## Sidecar

Communicate Between Containers in the Same Pod Using a Shared Volume

## Readiness Prope

add to the def yaml:
```
readinessProbe:
    httpGet:
        path: /api/ready
        port: 8080
    initialDelaySeconds: 10
    periodSeconds: 5
    failureThreshold: 8 ## no of attempts
```

## Liveness Prope

add to the def yaml:
```
livenessProbe:
    httpGet:
        path: /api/ready
        port: 8080
    initialDelaySeconds: 10
    periodSeconds: 5
    failureThreshold: 8 ## no of attempts
```