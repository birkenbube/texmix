FROM ghcr.io/dante-ev/texlive:edge
WORKDIR /tmp/dockerwork

ARG USERNAME=texmix
ARG USER_ID=1000
ARG USER_GID=${USER_ID}

# Update apt packages and make sure sudo is installed
RUN apt update && apt upgrade -y && apt install -y sudo

# Remove existing texlive user
RUN userdel -r texlive

# Setup user and enable passwordless sudo
RUN groupadd --gid ${USER_GID} ${USERNAME} && \
    useradd --uid ${USER_ID} --gid ${USER_GID} -m ${USERNAME} && \
    echo ${USERNAME} ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/${USERNAME} && \
    chmod 0440 /etc/sudoers.d/${USERNAME}

# update texlive packages
RUN tlmgr update --self --all

# pre-download ltex-ls (Removed due to ltex+ having very frequent updates)
# RUN wget -qO- https://github.com/valentjn/ltex-ls/releases/download/15.2.0/ltex-ls-15.2.0-linux-x64.tar.gz | \
#     tar -xz --strip-components=1
# RUN mv ltex-ls-15.2.0 /usr/lib

# Cleanup
RUN rm -rf /tmp/dockerwork
WORKDIR /workspace