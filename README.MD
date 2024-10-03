# CARD REST API

This repository contains a REST API for the [CARD (Cell-type Assignment of RNA-seq Data)](https://github.com/YMa-lab/CARD) package, used for cell deconvolution in spatial transcriptomics data. The API is implemented using `plumber` in R and is containerized with Docker for easy deployment.

All CARD credit belongs to Y.Ma et al.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Setup Instructions](#setup-instructions)
  - [Prerequisites](#prerequisites)
  - [Building and Running with Docker](#building-and-running-with-docker)
  - [Local Development](#local-development)
- [Endpoints](#endpoints)
  - [`/predict` (POST)](#predict-post)
  - [`/test` (GET)](#test-get)
  - [`/echo` (GET)](#echo-get)
- [Example REST API Calls](#example-rest-api-calls)
- [License](#license)

## Overview

The CARD REST API allows users to perform cell deconvolution using spatial transcriptomics data, providing an interface to interact with the CARD package in a programmatic way. This repository includes:

- R code implementing the CARD API with the `plumber` package.
- A Dockerfile for containerizing the API, making it easily deployable.

## Features

- **Cell Deconvolution**: Run the CARD deconvolution model through REST API endpoints.
- **Containerized Environment**: Deploy the API with Docker for portability and consistency.
- **Simple API Testing**: Test endpoints for easy health checks and message echoing.

## Setup Instructions

### Prerequisites

- **Docker**: You need Docker installed to build and run the container.
- **R (optional for local development)**: Version 4.3.1 or higher is recommended.

### Building and Running with Docker

1. **Clone the Repository**:
    ```sh
    git clone https://github.com/AlbertPlaPlanas/CARD-REST.git
    cd CARD-REST-API
    ```

2. **Build the Docker Image**:
    ```sh
    docker build -t card-api .
    ```

3. **Run the Docker Container**:
    ```sh
    docker run -p 8000:8000 card-api
    ```

   The API will be available at `http://localhost:8000`.

- Alternatively, download the Docker image from [DockerHub](https://hub.docker.com/r/albertplaplanas/card-api) and run the Docker container.

```sh
docker pull albertplaplanas/card-api
docker run -p 8000:8000 albertplaplanas/card-api
``

### Local Development

For local development without Docker:

1. **Install Dependencies**:
    Ensure you have the required R version and packages. Install dependencies by running:
    ```R
    source('requirements.R')
    ```

2. **Run the API**:
    ```sh
    Rscript run.R
    ```

## End
