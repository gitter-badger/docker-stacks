# Copyright (c) Jupyter Development Team.
FROM jupyter/minimal-notebook

MAINTAINER Jupyter Project <jupyter@googlegroups.com>

# R pre-requisites
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    libxrender1 \
    fonts-dejavu \
    gfortran \
    gcc && apt-get clean

USER jovyan

# R packages
RUN conda config --add channels r
RUN conda install --yes \
    'r-base=3.2*' \
    'r-irkernel=0.4*' \
    'r-plyr=1.8*' \
    'r-devtools=1.8*' \
    'r-dplyr=0.4*' \
    'r-ggplot2=1.0*' \
    'r-tidyr=0.2*' \
    'r-shiny=0.12*' \
    'r-rmarkdown=0.7*' \
    'r-forecast=5.8*' \
    'r-stringr=0.6*' \
    'r-rsqlite=1.0*' \
    'r-reshape2=1.4*' \
    'r-nycflights13=0.1*' \
    'r-caret=6.0*' \
    'r-rcurl=1.95*' \
    'r-randomforest=4.6*' && conda clean -yt

# Switch back to root so that supervisord runs under that user
USER root