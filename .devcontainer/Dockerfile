FROM mcr.microsoft.com/devcontainers/python:1-3.11-bullseye

# Set the working directory
WORKDIR /workspace

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