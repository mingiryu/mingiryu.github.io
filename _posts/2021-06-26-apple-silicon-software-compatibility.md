---
layout: posts
title: "Apple Silicon Software Compatibility"
updated: 2021-06-26
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

# Supported w/ Rosetta
- Numpy

# Not Supported
- Apache Spark & PySpark
  - `pyspark` can start w/ Rosetta & Docker, but it either hangs or throws JDK errors. 
