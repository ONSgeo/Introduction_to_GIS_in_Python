# Pre-built Dev Container Image for R. More info: https://github.com/rocker-org/devcontainer-images/pkgs/container/devcontainer%2Ftidyverse
# Available R version: 4, 4.1, 4.0
ARG VARIANT="4.2"
FROM ghcr.io/rocker-org/devcontainer/tidyverse:${VARIANT}

#RUN apt-get install software-properties-common \
#    && add-apt-repository ppa:ubuntugis/ppa -y

#RUN apt-get update

#RUN apt-get install gdal-bin -y \
#    && apt-get install libgdal-dev -y

# Install Python packages
COPY requirements.txt /tmp/pip-tmp/
RUN python3 -m pip --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt
