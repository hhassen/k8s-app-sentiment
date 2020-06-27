# Sentiment Analysis application
![](https://cdn-images-1.medium.com/max/1600/1*oH9lP-4GWT8eQHh_X5obsw.gif)

## Kubernetes
* Set up `minikube` to run Kubernetes locally.
#### Pods
* Launch **pods** manually
* Access to the application externally using port-forwarding: `kubectl port-forward sa-frontend 88:80`
* Duplicate the pod manually (the wrong way to do things)
#### Services
* Set up a Load Balancer **service** to access our target pods
* Apply **Labels** to the pods we want to access
* Apply a **Selector** to our service using that Labels
* `kubectl get pod -l app=sa-frontend`
#### Deployment
* Use Kubernetes **Deployment** to deploy each application
* Delete pods created manually : `kubectl delete pod <pod-name>`
* Delete one of the pods deployed : another one is automatically launched.
* Make a rollout to a new version: `kubectl apply -f sa-frontend-deployment-green.yaml --record`.
* Roll back to the previous version `kubectl rollout history deployment sa-frontend` and `kubectl rollout undo deployment sa-frontend --to-revision=1`
#### KUBE-DNS
* Get IP address of a service
#### Amazon EKS
* Migrate our local cluster to amazon EKS

![](https://cdn-media-1.freecodecamp.org/images/Rl5B3SRE5U5IiIM-8-1HnZdnwMx1TzegzV3D)

## Docker-Compose
To get up and running with the application execute:

```
$ docker-compose up
```

And open http://localhost

## Credits

Credits to [Rinor Maloku](https://medium.freecodecamp.org/learn-kubernetes-in-under-3-hours-a-detailed-guide-to-orchestrating-containers-114ff420e882) for the code and the original article.
