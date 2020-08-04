---
date: "2020-08-03T17:07:35+02:00"
title: "keptn send event new-artifact"
slug: keptn_send_event_new-artifact
---
## keptn send event new-artifact

Sends a new-artifact event to Keptn in order to deploy a new artifact for the specified service in the provided project

### Synopsis

Sends a new-artifact event to Keptn in order to deploy a new artifact for the specified service in the provided project.
Therefore, this command takes the project, service, image, and tag of the new artifact.

* The artifact is the name of a image, which can be located at DockerHub, Quay, or any other registry storing docker images. 
* The new artifact is pushed in the first stage specified in the Shipyard of the project. Afterwards, Keptn takes care of deploying this new artifact to the other stages.

**Notes:**
* The value provided in the *image* flag has to contain the full path to your Docker registry. The only exception is *docker.io* because this is the default in Kubernetes and, hence, can be omitted.
* This command does not send the actual Docker image to Keptn, just the image name and tag. Instead, Keptn uses Kubernetes functionalities for pulling this image.
For pulling an image from a private registry, we would like to refer to the Kubernetes documentation (https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/).


```
keptn send event new-artifact [flags]
```

### Examples

```
keptn send event new-artifact --project=sockshop --service=carts --image=docker.io/keptnexamples/carts --tag=0.7.0
```

### Options

```
  -h, --help             help for new-artifact
      --image string     The image name, e.g.docker.io/YOUR_ORG/YOUR_IMAGE or quay.io/YOUR_ORG/YOUR_IMAGE. Optionally, you can directly append the tag using ":YOUR_TAG"
      --project string   The project containing the service which will be new deployed
      --service string   The service which will be new deployed
      --tag string       The tag of the image. If no tag is specified, the "latest" tag is used.
```

### Options inherited from parent commands

```
      --mock                 Disables communication to a Keptn endpoint
  -q, --quiet                Suppresses debug and info messages
      --suppress-websocket   Disables WebSocket communication to suppress info messages from services running inside Keptn
  -v, --verbose              Enables verbose logging to print debug messages
```

### SEE ALSO

* [keptn send event](../keptn_send_event/)	 - Sends an event to Keptn

###### Auto generated by spf13/cobra on 3-Aug-2020