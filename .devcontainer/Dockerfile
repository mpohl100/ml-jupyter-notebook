#Use microsoft devcontainer
ARG VARIANT=bullseye
FROM mcr.microsoft.com/vscode/devcontainers/rust:1-${VARIANT}

# Set the working directory
WORKDIR /workspace

# Install Python using apt
RUN apt-get update && apt-get install -y python3 python3-pip python3-venv \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install Jupyter Notebook and other dependencies
RUN pip install --upgrade pip \
    && pip install jupyter notebook \
    && apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    curl \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY requirements.txt /workspace/
RUN pip install -r requirements.txt

# Expose Jupyter port
EXPOSE 8888

# Set the default command (optional, helpful for debugging)
CMD ["bash"]