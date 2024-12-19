# Rancher Desktop exploration

This repository has been archived.

This repository was created to explore the use of Rancher Desktop for local
development of the OGDC. QGreenland-Net developers have adopted Rancher Desktop.

## Linux installation

Followed
[.deb install instructions](https://docs.rancherdesktop.io/getting-started/installation/#installation-via-deb-package).


## Hello world

* Files in this repo created following
[hello world example](https://docs.rancherdesktop.io/how-to-guides/hello-world-example/)
instructions.
* Run command to build the image and then view it:

    ```
    docker build --tag nginx-helloworld:latest .
    docker images | grep nginx-helloworld
    ```

* Deploy to k8s:

    ```
    kubectl run hello-world --image=nginx-helloworld:latest --image-pull-policy=Never --port=80
    kubectl port-forward pods/hello-world 8080:80
    ```

    > [!IMPORTANT]
    >
    > You will need to wait in between these commands, or you may receive `error: unable
    > to forward port because pod is not running. Current status=Pending`.
    >
    > Once the second command is run, your shell will be captured.

* Visit `localhost:8080` to view a lovely message.
