FROM ubuntu:22.04
CMD bash

RUN cd ~ && \
    apt -y update && apt -y upgrade && \
    echo yes | apt -y install curl git wireshark tcpdump && \
    # Install kubectl
    curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256" && \
    install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl && \
    # Install Krew
    set -x; cd "$(mktemp -d)" && \
    OS="$(uname | tr '[:upper:]' '[:lower:]')" && \
    ARCH="$(uname -m | sed -e 's/x86_64/amd64/' -e 's/\(arm\)\(64\)\?.*/\1\2/' -e 's/aarch64$/arm64/')" && \
    KREW="krew-${OS}_${ARCH}" && \
    curl -fsSLO "https://github.com/kubernetes-sigs/krew/releases/latest/download/${KREW}.tar.gz" && \
    tar zxvf "${KREW}.tar.gz" && \
    ./"${KREW}" install krew && \
    export PATH="${KREW_ROOT:-$HOME/.krew}/bin:$PATH" && \
    # Install ksniff
    kubectl krew install sniff
