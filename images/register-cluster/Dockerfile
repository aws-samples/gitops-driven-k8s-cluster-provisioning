FROM alpine:3.19

RUN echo "http://dl-4.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories

RUN apk update && apk add --no-cache aws-cli jq curl bash git coreutils yq

RUN curl -sSL -o argocd-linux-amd64 https://github.com/argoproj/argo-cd/releases/latest/download/argocd-linux-amd64 && \
    install -m 555 argocd-linux-amd64 /usr/local/bin/argocd && \
    rm argocd-linux-amd64 

RUN useradd -d /home/argo -m -s /bin/bash argo
USER username