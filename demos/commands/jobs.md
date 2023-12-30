# Jobs

Create a job with the specified name.

## Examples:

Create a job
```
kubectl create job my-job --image=busybox
```

Create a job with a command
```
kubectl create job my-job --image=busybox -- date
```

Create a job from a cron job named "a-cronjob"
```
kubectl create job test-job --from=cronjob/a-cronjob
```

