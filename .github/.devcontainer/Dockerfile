FROM ghcr.io/dante-ev/texlive:edge
WORKDIR /tmp/dockerwork

# pre-download ltex-ls
RUN wget -qO- https://github.com/valentjn/ltex-ls/releases/download/15.2.0/ltex-ls-15.2.0-linux-x64.tar.gz | \
tar -xz --strip-components=1
RUN mv ltex-ls-15.2.0 /usr/lib

# Custom cache invalidation
ARG CACHEBUST=1

# Always update texlive packages
RUN tlmgr update --self --all

# Cleanup
RUN rm -rf /tmp/dockerwork
WORKDIR /workspace