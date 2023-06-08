# Pre-built Dev Container Image for R. More info: https://github.com/rocker-org/devcontainer-images/pkgs/container/devcontainer%2Ftidyverse
# Available R version: 4, 4.1, 4.0
ARG VARIANT="4.2"
FROM ghcr.io/rocker-org/devcontainer/tidyverse:${VARIANT}

RUN apt-get update && apt-get install -y --no-install-recommends \
        software-properties-common \
        libudunits2-dev \
        libgdal-dev \
        libgeos-dev \
        libproj-dev

RUN add-apt-repository ppa:ubuntugis/ppa -y \
        && apt-get install -y --no-install-recommends gdal-bin

RUN pip uninstall Jinja2

#RUN apt-get update && apt-get install -y \
#        && software-properties-common
#        && libudunits2-dev \
#        && libgdal-dev \
#        && libgeos-dev \
#        && libproj-dev 
#        #&& add-apt-repository ppa:ubuntugis/ppa
        
#RUN apt-get update \
#        && apt-get install -y --no-install-recommends \
#        && apt-get install gdal-bin

# Install Python packages
COPY requirements.txt /tmp/pip-tmp/
RUN python3 -m pip --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt
