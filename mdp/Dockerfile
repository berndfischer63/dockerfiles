FROM debian:jessie
MAINTAINER Jessica Frazelle <jess@docker.com>

RUN apt-get update && apt-get install -y \
    ca-certificates \
    gcc \
    git \
    libncurses5 \
    libncurses5-dev \
    libncursesw5 \
    libncursesw5-dev \
    make \
    --no-install-recommends

RUN git clone --recursive https://github.com/visit1985/mdp.git /src

WORKDIR /src

ENV TERM    xterm-256color
ENV DEBUG   1 

RUN make \
    && make install

ENTRYPOINT [ "/usr/local/bin/mdp" ]
