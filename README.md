# Jupyter notebooks

Dockerfiles for building various flavours of Jupyter notebook

1. Minimal notebook with latest RDKit release [Dockerfile-rdkit-release-latest](Dockerfile-rdkit-release-latest)
1. Minimal notebook with latest RDKit beta [Dockerfile-rdkit-beta](Dockerfile-rdkit-beta) (Look at the deatils in [Anaconda](https://anaconda.org/rdkit/rdkit) for what this currently relates to)

NOTE: these Docker images are quite large and take some time to download!

## Running

Launch Jupyter with a command like this:
```
docker run -p 8888:8888 -e NB_UID=501 -e NB_GID=20 --user root -v /path/to/your/jupyter_notebooks/:/home/jovyan/work informaticsmatters/rdkit_jupyter start-notebook.sh
```

The NB_UID and NB_GID are specified so that files are created as your user ID. Adjust the values accordingly to match your user ID and group. The --user root is needed to allow the  NB_UID and NB_GID to be specified.

Adjust `/path/to/your/jupyter_notebooks` to the location where yoy want your notebooks to be located on the host machine.

When you run this command a link with a token is written to the console. Open this in your web browser and you should be up and running.

NOTE: this approach is not suitable for publically facing machines. Additional security measures need to be put in place. See the Jupyter docs for more on this.

