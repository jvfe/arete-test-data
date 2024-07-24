FROM r-base:4.3.0

LABEL image.author.name "jvfecav"

# Get Cpp
RUN apt-get update && \
    apt-get -y install gcc mono-mcs libglpk-dev libxml2 libxml2-dev procps && \
    rm -rf /var/lib/apt/lists/*

RUN Rscript -e "install.packages(c('ape', 'dplyr', 'phytools', 'foreach', 'doParallel', 'gplots', 'remotes'))"
RUN Rscript -e "remotes::install_github('beiko-lab/evolCCM')"

CMD ["bash"]
