# Commands

## Service Account

Aliases:
serviceaccount, sa

Create a new service account named my-service-account
```
kubectl create serviceaccount my-service-account
```

to create a token for that serviceaccount
```
k create token <same-name-of-serviceaccount>
```
