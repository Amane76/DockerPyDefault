# Personal Python Development Environment

Created by Tabetaaaaaaa.
A containerized basic Python development environment using Docker and VSCode Dev Containers.

## Purpose

This container contains only the basic tools used for python development.
You can clone it and add the tools and settings you need as needed.

## Features

- Python 3.13 environment
- Poetry for dependency management
- Pre-configured VSCode extensions for Python development
- Git integration

## Prerequisites

- Docker
- VSCode
- Dev Containers extension for VSCode

## Getting Started

1. Clone this repository
2. Open in VSCode
3. Execute the following commands in Terminal.

   ``` bash
    cd ./.devcontainer
    docker-compose build
    docker-compose up -d
    ```

4. Click "Reopen in Container" when prompted. Or execute a following command.

   ``` bash
    docker-compose exec python /bin/bash
    ```

5. Start developing!

## Container Specifications

- Base image: `python:3.13-slim`
- Package manager: Poetry
- Working directory: `/workspace`
- Pre-installed tools:
  - Git
  - Curl
  - basic-essentiail
  - VSCode Extentions
    - Python
    - Jupyter
    - GitHub Copilot
    - Git Graph
    - Markdown support
    - CSV tools
    - And more...

## Notes

- Auto-save is enabled
- Japanese language support included
- Custom icon theme configured
