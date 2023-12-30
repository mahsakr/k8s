# Resources

* https://github.com/lucassha/CKAD-resources
* https://ericsson.udemy.com/labs/listing/
* https://medium.com/@atharvac.cloud/my-ckad-exam-experience-5e10c3640273
* https://medium.com/@harioverhere/ckad-certified-kubernetes-application-developer-my-journey-3afb0901014

## k8s

* kubectl reference docs: https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#create


```
k create ingress ingress-wear-watch -n app-space --rule="/wear=wear-service:8080" --rule="/watch=video-service:8080" --dry-run=client -o yaml
```

```
k create ingress ingress-app -n app-space --rule="/wear=wear-service:8080" --rule="/watch=video-service:8080" --nginx.ingress.kubernetes.io/rewrite-target="/"--dry-run=client -o yaml
```