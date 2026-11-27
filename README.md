# FE2_Documentation

[![Built with Zensical](https://img.shields.io/badge/Built%20with-Zensical-526CFE?style=for-the-badge)](https://zensical.org/)

**[Access the documentation](https://ffw-baudenbach.github.io/FE2_Documentation/)**

The documentation website is automatically generated from the [`docs/`](docs/) folder whenever changes are pushed to the `main` branch.

## How it works

This project uses [Zensical](https://zensical.org/) to generate a static HTML website from Markdown files.

The generated website is hosted on **GitHub Pages** directly through this repository.

Changes to documentation in the [`docs/`](docs/) folder on the `main` branch automatically trigger the build and deployment process.

Configuration is managed through the [`mkdocs.yaml`](mkdocs.yaml) file.

## How to develop locally

1. Install [Python](https://www.python.org/).
2. Clone this repository.
3. Install the required dependencies:

   ```bash
   pip install --upgrade -r requirements.txt