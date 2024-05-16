FROM nvidia/cuda:12.1.0-cudnn8-devel-ubuntu22.04

RUN apt update -y && apt upgrade -y && apt install -y --no-install-recommends  \
    git \
    git-lfs \
    python3 \
    python3-pip \
    python3-dev \
    wget \
    curl \
    vim \
	gcc \
	g++ \
&& rm -rf /var/lib/apt/lists/*


# pip
RUN pip install --upgrade pip

# torch
RUN pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121 --no-cache

# unsloth
RUN pip3 install "unsloth[cu121] @ git+https://github.com/lianshufeng/unsloth.git"

RUN pip3 install --no-deps "xformers<0.0.26" trl peft accelerate bitsandbytes
