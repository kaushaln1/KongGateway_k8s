# KongGateway_k8s

This repository contains the configurations and scripts to set up and manage Kong API Gateway on a Kubernetes cluster. The goal of this project is to understand and implement microservice architecture using the Kong API Gateway.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)

## Introduction

Kong is an open-source API gateway and microservices management layer that provides a way to manage, monitor, and control API traffic. This project demonstrates the deployment of Kong Gateway on a Kubernetes cluster, enabling you to explore its features and capabilities in a microservice architecture.

## Prerequisites

Before you begin, ensure you have the following installed:

- [Kubernetes](https://kubernetes.io/docs/setup/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Helm](https://helm.sh/docs/intro/install/)
- [Docker](https://docs.docker.com/get-docker/)

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/kaushaln1/KongGateway_k8s.git
    cd KongGateway_k8s
    ```

2. **Deploy Kong Gateway using Helm:**
    ```bash
        helm install kong .\helm\kong\ --namespace kong 
    ```
    This will also deploy a test app "echo server" as we ahve bundled it in helm with additional policy (rate-limiting) applied on it.  

3. **Verify the deployment:**
    ```bash
    kubectl get all -n kong
    ```

## Configuration

Configuration details for Kong Gateway can be found in the `values.yaml` file. This file allows you to customize various aspects of Kong Gateway, such as database settings, service configurations, and plugins.

1. Currently using in DB-less mode. 


## Usage

1. **Test the route:**
    ```bash
    curl -i -X GET http://localhost:80/echo
    ```
