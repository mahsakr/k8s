# Commands

## Replicaset

Aliases:
deployment, deploy


explain type (replicaset , pod, .)
```
kubectl explain deployment
```

create deployment from file 
```
kubectl create -f deployment-def.yml
```

get deployment 
```
kubectl get deployments
```

get all objects created by the deplyment
```
kubectl get all
```

Create a deployment named my-dep that runs the busybox image
```
kubectl create deployment my-dep --image=busybox
```

Create a deployment with a command
```
kubectl create deployment my-dep --image=busybox -- date
```

Create a deployment named my-dep that runs the nginx image with 3 replicas
```
kubectl create deployment my-dep --image=nginx --replicas=3
```

Create a deployment named my-dep that runs the busybox image and expose port 5701
```
kubectl create deployment my-dep --image=busybox --port=5701
```

Generate Deployment YAML file (-o yaml). Don't create it(--dry-run)
```
kubectl create deployment --image=nginx nginx --dry-run -o yaml
```


Generate Deployment with 4 Replicas
```
kubectl create deployment nginx --image=nginx --replicas=4
```

You can also scale deployment using the kubectl scale command.
```
kubectl scale deployment nginx --replicas=4
```

Another way to do this is to save the YAML definition to a file and modify
```
kubectl create deployment nginx --image=nginx--dry-run=client -o yaml > nginx-deployment.yaml
```


You can then update the YAML file with the replicas or any other field before creating the deployment.

Create a new deployment called redis-deploy in the dev-ns namespace with the redis image. It should have 2 replicas.
```
k create deploy redis-deploy --image=redis --replicas=3 -n dev-nsdeployment.apps/redis-deploy created
```

## Edit Deployments
With Deployments you can easily edit any field/property of the POD template. Since the pod template is a child of the deployment specification,  with every change the deployment will automatically delete and create a new pod with the new changes. So if you are asked to edit a property of a POD part of a deployment you may do that simply by running the command
```
kubectl edit deployment my-deployment
```