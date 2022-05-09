# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.231.6/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version (use hirsuite or bionic on local arm64/Apple Silicon): hirsute, focal, bionic
ARG VARIANT="hirsute"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
  && apt-get -y install --no-install-recommends openmpi-bin libopenmpi-dev g++ make gdb ruby-dev x86info linux-tools-generic

# Install cairo required for day5's visualization.
RUN gem install cairo

# Configure perf tool.
RUN rm -rf /usr/bin/perf && \
  ln -s /usr/lib/linux-tools/5.4.0-109-generic/perf /usr/bin/perf
