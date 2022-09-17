# GCC

This is Dockerfile for GCC/G++ compile environment

## Usage

From the repository directory, run these commands to create a Docker image and container:

```bash
docker build . -t gcc
docker create -it --name gcc -v $(pwd):/gcc gcc bash
```

This will create a Docker image and container. To run it, type:
```bash
docker start -a -i gcc
```
