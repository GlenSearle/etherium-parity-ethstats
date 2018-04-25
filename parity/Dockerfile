FROM ubuntu:14.04
#WORKDIR /build

# install tools and dependencies
RUN apt-get update && \
        apt-get install -y \
        g++ \
        build-essential \
        curl \
        git \
        file \
        binutils \
        libssl-dev \
        pkg-config \
        libudev-dev

# install rustup
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y

# rustup directory
ENV PATH /root/.cargo/bin:$PATH

# show backtraces
ENV RUST_BACKTRACE 1

# show tools
RUN rustc -vV && \
cargo -V && \
gcc -v &&\
g++ -v

# build parity
#ADD . /build/parity
RUN cd / && \
    git clone https://github.com/paritytech/parity && \
        cd parity/parity && \
        cargo build --release --verbose && \
        ls /parity/parity/target/release/parity && \
        strip /parity/parity/target/release/parity

RUN file /parity/parity/target/release/parity

EXPOSE 8080 8545 8180
ENTRYPOINT ["/parity/parity/target/release/parity"]
