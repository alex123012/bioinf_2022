FROM r-base:4.2.2

RUN apt-get update && \
    apt-get install -y \
        libcurl4-openssl-dev \
        libxml2-dev \
        libxslt-dev \
        libssl-dev \
        python3.10 \
        python3-pip \
        python3-dev \
        vim

COPY /install_packages.r /app/install_packages.r
RUN Rscript /app/install_packages.r

COPY /requirements.txt /app/requirements.txt
RUN pip install -r /app/requirements.txt && \
    pip cache purge

ENTRYPOINT ["bash", "-c"]
CMD [""]
WORKDIR /code