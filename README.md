# mf6-docker
Running USGS ModFlow 6 i a Docker container

This is a Proof Of Concept project, that demonstrates building a ubuntu-based docker-container with USGS Modflow 6 installed. Running the container will run model-files in the containers directory /workspace/models. 

## Try it out
To use the Docker image, you need to have Docker installed - see [[https://docs.docker.com/engine/install/]] for instructions about this.

Then:
- Clone the repository to your desktop
- cd into the cloned directory (mf6-docker)
- Build and run the container:
```shell
docker build -t mf6-test .
```

Wach the autpu, and after the build is done:
```shell
docker run -it mf6-test
```

If everything worked, this will result in the help-command of Modflow 6. This is because the containers model directory is empty - to run an actual model, link a directory with modflow data-files and a "mfsim.nam" file, to the containers models directory - see example below.

## To test it wiht an example model from the installation bundle
````shell
docker run -it -v "${PWD}/models":/workspace/models mf6-test
```
... and watch the output
