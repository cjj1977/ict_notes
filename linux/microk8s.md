# microk8s

## About

## Notes

### Installation

* Instructions at: [ubuntu.com/tutorials](https://ubuntu.com/tutorials/install-a-local-kubernetes-with-microk8s)
* Using Ubuntu 20.04
* Installation uses [snap](./snap.md)

``` bash
sudo snap install microk8s --classic
sudo microk8s enable dns dashboard storage
```

#### Check status of add-ons

``` bash
microk8s kubectl get all --all-namespaces
```

### Example deployment

The following example creates a Deployment called **microbot** and exposes port
80 from the bot using a NodePort (with a random host port):

``` bash
microk8s kubectl create deployment microbot --image=dontrebootme/microbot:v1
microk8s kubectl scale deployment microbot --replicas=2

microk8s kubectl expose deployment microbot --type=NodePort --port=80 --name=microbot-service
```

### Using the registry

microk8s cannot access the local docker image repository directly. You can use
an image registry service (the **registry** add-on) and push images into
microk8s.

* [Build apps locally and Deploy on MicroK8s](/https://medium.com/manikkothu/build-and-deploy-apps-on-microk8s-1df26d1ddd3c)

#### Enabling the registry

``` bash
sudo microk8s enable registry
```

By default the registry listens on (is mapped to) port **32000** of the host.

#### Docker images

You can see what images you have in docker using:

``` bash
sudo docker images
```

And you add images (to docker) using a command similar to the following from the
root folder of your app project folder (where the `Dockerfile` is found). Rather
than simply building the image as usual, you can specify the microk8s registry
as the "username" for the build and then **push** the image to the registry:

``` bash
# docker build -t <username>/<image-name>:<tag> .
sudo docker build -t localhost:32000/my-app:tag .

sudo docker push localhost:32000/my-app:tag
```

