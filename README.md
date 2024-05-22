# TeXmIx
A simple devcontainer for VSCode with TeX Live and other tools preinstalled

> [!WARNING]  
> Use at your own risk as I am still working on this.

## What is this?
This simple devcontainer utilizes the awesome [Docker image for texlive](https://github.com/dante-ev/docker-texlive) and adds [devcontainer features](https://containers.dev/features) required for Visual Studio Code, namely:
- [common-utils](https://github.com/devcontainers/features/tree/main/src/common-utils)
- [git](https://github.com/devcontainers/features/tree/main/src/git)

## Why?
All devcontainers I found had some issue, mostly with user permissions, missing packages or they were no longer maintained. This devcontainer aims to be configured as minimally as possible while providing all required texlive packages.