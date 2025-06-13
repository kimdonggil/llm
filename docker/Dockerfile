# Base image
#FROM nvidia/cuda:11.4.3-devel-ubuntu20.04
FROM nvidia/cuda:11.8.0-devel-ubuntu20.04

# Set timezone and avoid interactive prompts
ENV TZ=Asia/Seoul
ARG DEBIAN_FRONTEND=noninteractive

# Install essential packages, tzdata (for timezone), and Python 3.9
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    git \
    build-essential \
    python3.9 \
    python3.9-dev \
    python3-pip \
    curl \
    libatlas-base-dev \
    libopenblas-dev \
    libomp-dev \
    tzdata && \
    rm -rf /var/lib/apt/lists/*

# Set Python 3.9 as the default
RUN update-alternatives --install /usr/bin/python python /usr/bin/python3.9 1 && \
    update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.9 1 && \
    update-alternatives --set python /usr/bin/python3.9 && \
    update-alternatives --set python3 /usr/bin/python3.9

# Upgrade pip
RUN python3 -m pip install --upgrade pip

# Copy the requirements.txt into the container and install Python dependencies
COPY requirements.txt /tmp/
RUN pip install -r /tmp/requirements.txt

# Install PyTorch (CUDA 11.8)
RUN pip install torch==2.1.2+cu118 torchvision==0.16.2+cu118 torchaudio==2.1.2+cu118 \
    --extra-index-url https://download.pytorch.org/whl/cu118

# Clean up unnecessary files to reduce image size
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm /tmp/requirements.txt

# Set the default command to bash
CMD ["/bin/bash"]

