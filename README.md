# SPITE Vulkan Graphics Engine - Documentation

This repository contains source files for the official documentation of the [SPITE Vulkan Graphics Engine](https://github.com/likhachev-mischa/SPITE-Engine).

The documentation is built using [MkDocs](https://www.mkdocs.org/) with the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme.

## Live Documentation

The documentation is hosted at [docs.spiteful.ru](https://docs.spiteful.ru).

## About the Engine

The SPITE (Scalable Performance-Intensive Technology Engine) is a modern 3D graphics engine built on data-oriented design principles and leveraging the Vulkan API for maximum performance. The engine employs an Entity-Component-System (ECS) architecture to manage complex rendering scenarios while maintaining high performance and scalability.

### Key Features

- **Data-Oriented Design**: Optimized for cache locality and parallel processing.
- **ECS Architecture**: Modular and extensible component-based system.
- **Vulkan Integration**: Low-overhead GPU control with explicit resource management.
- **Deferred Rendering**: Multi-pass rendering pipeline for complex lighting scenarios.
- **Cross-Platform**: Designed for cross-platform potential.

## Repository Structure

- `mkdocs.yml`: The MkDocs configuration file.
- `docs/`: Contains the Markdown source files for the documentation.

## Usage guide

Install python >= 3.12 on your machine. Then create virtual environment with `python -m venv .venv` (or use `python3`).
Install mkdocs and mkdocs-material with `pip install mkdocs` and `pip install mkdocs-material`

To run development server do:
1. Navigate to the docs-spite/ dir
2. Run `mkdocs serve`
3. Open `localhost:8000`
