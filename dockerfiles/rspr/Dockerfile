FROM python:3.9.16-slim-buster

LABEL image.author.name "jvfecav"

# Get curl/unzip
RUN apt-get update &&\
    apt-get install -y curl unzip build-essential && \
    rm -rf /var/lib/apt/lists/*

# Install rspr
RUN curl -L \
    https://github.com/cwhidden/rspr/archive/refs/heads/master.zip \
    -o rspr.zip &&\
    unzip rspr.zip &&\
    cd rspr-master &&\
    make

ENV PATH=/rspr-master:$PATH

# Install Python script dependencies
RUN pip install pandas ete3 seaborn>0.13.0

# Install BioPython and dependencies
RUN apt-get update &&\
    apt-get install -y graphviz graphviz-dev
RUN pip install biopython networkx pygraphviz pydot

# Get ps
RUN apt-get update && apt-get install -y procps && rm -rf /var/lib/apt/lists/*

CMD ["bash"]