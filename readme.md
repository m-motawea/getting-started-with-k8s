### k8s getting started labs:
this repo includes some stuff used when trying k8s for the first time

##### Installation:
https://vitux.com/install-and-deploy-kubernetes-on-ubuntu/

##### Nginx Ingress Controller:
https://docs.nginx.com/nginx-ingress-controller/installation/installation-with-manifests/


##### Usage:
1- First Pod:
create a pod and expose it over node port.

* create pod
```bash
$ kubectl apply -f pods/nginx-pod-1.yml
```

* create a service to expose your pod
```bash
$ kubectl apply -f services/nginx-service-1.yml
```


2- First Deployment:

create a deployment of nginx with 3 rplicas

```bash
$ kubectl apply -f deployments/nginx-deployment-1.yml
```


3- Create a Config Map:

this config map will contain nginx config, ssl cert and key to be used to deploy nginx

```bash
$ kubectl apply -f configmaps/nginx-ssl-1.yml
```


4- Nginx SSL Deployment:

will use the created config map to create a volume and mount it in nginx containers

```bash
$ kubectl apply -f deployments/nginx-ssl-deployment-1.yml
```


5- Check your Deployment History

```bash
$ kubectl rollout history deploy nginx-deployment
```


6- Rollback to Previous Deployment

```bash
$ kubectl rollout undo deploy nginx-deployment
```


7- 