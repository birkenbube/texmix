FROM ghcr.io/dante-ev/texlive:edge
WORKDIR /tmp/dockerwork
# update texlive packages
RUN tlmgr update --self --all

# pre-download ltex-ls
RUN wget -O- https://github.com/valentjn/ltex-ls/releases/download/15.2.0/ltex-ls-15.2.0-linux-x64.tar.gz | \
    tar -xz --strip-components=1
RUN mv ltex-ls-15.2.0 /usr/lib

# Cleanup
RUN rm -rf /tmp/dockerwork
WORKDIR /workspace