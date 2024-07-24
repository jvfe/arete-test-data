FROM python:3.9.16-slim-buster

LABEL image.author.name "jvfecav"

# Get curl/unzip
RUN apt-get update &&\
    apt-get install -y curl unzip build-essential && \
    rm -rf /var/lib/apt/lists/*

# Install Python script dependencies

RUN pip install pandas ete3 seaborn>0.13.0 UpSetPlot

# Get ps
RUN apt-get update && apt-get install -y procps && rm -rf /var/lib/apt/lists/*

CMD ["bash"]
