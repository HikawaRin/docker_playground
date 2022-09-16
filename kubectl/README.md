# kubectl

This is Dockerfile for [kubectl](https://kubernetes.io/docs/reference/kubectl/) with [ksniff](https://github.com/eldadru/ksniff) plugin, which utilize [tcpdump](https://www.tcpdump.org/) and [Wireshark](https://www.wireshark.org/) to start a remote capture on any pod in your Kubernetes cluster. 

## Usage

From the repository directory, run these commands to create a Docker image and container:

```bash
docker build . -t kubectl
# if you want to load kubeconfig, you can copy your kubeconfig file under this directory then create a symbols link
docker create -it --name kubectl -v $(pwd):/kubectl kubectl bash
```

This will create a Docker image and container. To run it, type:
```bash
docker start -a -i kubectl
```
