FROM dfissore/latex2025

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository universe && \
    apt-get update && \
    apt-get install -y \
        opam \
        m4 \
        build-essential \
        curl \
        git \
        bubblewrap \
        unzip && \
    rm -rf /var/lib/apt/lists/*

RUN opam init --disable-sandboxing -y
RUN opam switch create 4.14.1
RUN eval $(opam env)
RUN opam install -y elpi.3.4.2

VOLUME ["/data"]
WORKDIR /data

ENTRYPOINT ["make"]
