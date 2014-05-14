# export XC_OS="darwin"
# export XC_ARCH=amd64
# docker run -i -t -e TESTFLAGS -e DOCKER_GRAPHDRIVER -e DOCKER_EXECDRIVER  --privileged docker-dev  /bin/bash

FROM  docker-dev


RUN apt-get install -y zip
RUN go get github.com/laher/goxc
RUN go get github.com/hashicorp/serf
ENV PATH $PATH:/gon/bin

WORKDIR /go/src/github.com/hashicorp/serf
RUN make

ENTRYPOINT ["/bin/bash", "-c"]
CMD ./scripts/dist.sh
