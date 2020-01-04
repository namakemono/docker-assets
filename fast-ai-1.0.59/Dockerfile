FROM nvidia/cuda:10.0-cudnn7-runtime

RUN apt update -y && apt install -y --no-install-recommends \
        build-essential \ 
        curl \
        git \ 
        make \
        python3-pip \ 
        python3-dev \
        python3-setuptools \
        unzip \ 
        vim \ 
        wget 

# Install python libraries
COPY ./requirements.txt /tmp/
RUN pip3 install --upgrade pip
RUN pip3 install -r /tmp/requirements.txt

# Launch Jupyter
WORKDIR /notebook
EXPOSE 8888
CMD jupyter notebook --port 8888 --ip=0.0.0.0 --allow-root --no-browser
