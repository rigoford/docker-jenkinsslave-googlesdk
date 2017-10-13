# docker-jenkinsslave-gcloud

Jenkins slave docker image with the following software installed

* Google Cloud SDK 159.0.0
* Terraform 0.10.7

## Usage

Available on [Docker Hub](https://hub.docker.com/r/rigoford/docker-jenkinsslave-gcloud/):

```
docker pull rigoford/docker-jenkinsslave-gcloud:alpha
```

To create a basic Jenkins slave instance use:

```
docker run \
    --detach \
    --env JENKINS_MASTER=<JENKINS_MASTER_ADDRESS> \
    --env JENKINS_USERNAME=<JENKINS_USERNAME> \
    --env JENKINS_PASSWORD=<JENKINS_PASSWORD> \
    --env JENKINS_EXECUTORS=1 \
    --env JENKINS_LABELS=gcloud \
    --env JENKINS_NAME=gcloud-slave \
    --env LANG=C.UTF-8 \
    --name jenkins_gcloud \
    --volume /etc/localtime:/etc/localtime:ro \
    docker-jenkinsslave-gcloud:alpha
```

Obviously you'll need an instance of Jenkins master running, I can recommend
[garethjevans/jenkins](https://hub.docker.com/r/garethjevans/jenkins).
