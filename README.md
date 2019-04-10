# Docker images supported by the Behavior and Neuroimaging Core

## Builinding the images

* Clone this repository.


* Run the build script to generate Docker images.

```
./docker_build.bash [ -r REGISTRY ] [ image_folder ]
```

The `-r` is the docker container registry. Building a given image, will build all dependants maintained in this repositore

For example to build the singleuser image, you would run 
`./docker_build.bash -r brownbnc dicomlistener`

Each docker image is tagged with the git commit hash corresponding with the last git revision of the build files. A `latest` tag is also pushed 


## File / Folder structure

:warning: The subdirectories names are hierachical, where `-` separates dependant images. During the buidl process, dependent images are build in order. 
