# decentralized_models

## Docker Guide
Build container:

```docker build --build-arg BASE_IMAGE=pytorch/pytorch:1.3-cuda10.1-cudnn7-devel -t apex .```

Run container with interactive shell:

```docker run --runtime=nvidia -it -v $(pwd):/workspace apex```

Run command in container:

```docker run --runtime=nvidia -v $(pwd):/workspace apex COMMAND```

Build container extended with Jupyter Lab:

```docker build --build-arg BASE_IMAGE=apex -t apex-jlab .```

Run container with Jupyter Lab (port 8888):

```docker run --runtime=nvidia -it -p 8888:8888 -v $(pwd):/workspace apex-jlab```

Run container with Jupyter Lab (different port):

```docker run --runtime=nvidia -it -p 8888:8888 -v $(pwd):/workspace apex-jlab jupyter-lab --ip=0.0.0.0 --port=PORT --allow-root```