# Dockerfile

FROM pytorch/pytorch:2.2.2-cuda12.1-cudnn8-runtime

RUN sed -i -e 's/archive.ubuntu.com/mirrors.tencentyun.com/g' /etc/apt/sources.list  && \
    sed -i -e 's/security.ubuntu.com/mirrors.tencentyun.com/g' /etc/apt/sources.list  && \
    # sed -i -e 's/https:\/\/developer.download.nvidia.com\/compute\/cuda\/repos/http:\/\/mirrors.tencent.com\/nvidia-cuda/g' /etc/apt/sources.list.d/cuda-ubuntu2204-x86_64.list && \
    apt-get update -y && \
    apt-get dist-upgrade -y && \
    apt-get install -y apt-utils bc wget git git-lfs python3-pip python-is-python3 libcairo2-dev pkg-config python3-dev python3.10-venv libgoogle-perftools4 libtcmalloc-minimal4 && \
    apt-get autoclean -y && \
    apt-get autoremove -y && \
    rm -rf /var/lib/apt/lists/* && \
    sed -i -e 's/mirrors.tencentyun.com/mirrors.tencent.com/g' /etc/apt/sources.list  && \
    mkdir -p /workspace && \
    adduser --disabled-password --gecos '' user && \
    chown -R user:user /workspace

# RUN conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/ && \
#     conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/ && \
#     conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/ && \
#     conda config --set show_channel_urls yes &&\
#     conda update -n base -c defaults conda &&\
#     pip config set global.index-url https://mirrors.tencent.com/pypi/simple

RUN conda install pytorch torchvision torchaudio pytorch-cuda=12.1 -y
