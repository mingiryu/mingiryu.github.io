---
layout: posts
title: "Apple Silicon Software Compatibility"
updated: 2021-06-28
category: posts
---

# Supported Natively
- Docker & Compose
  - Incorrect CPU usage reporting.
  - `docker` & `docker-compose` from `brew` conflicts with Docker Desktop.
- Poetry
- Terraform
  - Requires compiling `terraform-provider-template` from source.
- Ansible
- Git
- VS Code
- AWS CLI
- Vim
- iTerm
- Numpy
- Scipy
  - [scipy/issues/13409](https://github.com/scipy/scipy/issues/13409)
  - ```
    brew install openblas
    export OPENBLAS=$(brew --prefix openblas)
    export CFLAGS="-falign-functions=8 ${CFLAGS}"
    pip install scipy
    ```
- Tokenizers
  - [tokenizers/python/latest/installation/main.html#installation-from-sources](https://huggingface.co/docs/tokenizers/python/latest/installation/main.html#installation-from-sources)
- Scikit-learn (miniforge)
- Torch (miniforge)
- PyArrow (miniforge)
- PySpark (miniforge)

# Not Supported
- Apache Spark & PySpark (Poetry)
  - `pyspark` can start w/ Rosetta & Docker, but it either hangs or throws JDK errors. 
- Apache Arrow & PyArrow (Poetry)
