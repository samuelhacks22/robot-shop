# Stan’s Robot Shop – Microservices Application

This repository contains Stan’s Robot Shop, a microservices-based sample application that I implemented as a hands-on project to practice containerized architectures, service orchestration, observability, and distributed monitoring.

This project is intended for learning and experimentation purposes. It is not designed as a production-ready reference. Error handling is limited and no security mechanisms are included by default.

## Project Purpose

The main purpose of this project is to serve as a technical sandbox to strengthen practical skills in modern backend and cloud-native development. Through this application, I focused on working with containerized microservices, understanding service-to-service communication, deploying applications using different orchestration strategies, and analyzing system behavior through monitoring and tracing tools.

## Architecture Overview

The application follows a microservices architecture composed of independent services implemented using multiple programming languages and frameworks. Each service is containerized and communicates with others over well-defined APIs.

The frontend is built as a single-page application and is served through a reverse proxy. Backend services handle business logic, data persistence, messaging, and payment simulation. Supporting infrastructure services provide caching, messaging, and data storage.

## Technologies Used

Backend and frontend services are implemented using Node.js with Express, Java with Spring Boot, Python with Flask, Golang, PHP running on Apache, and AngularJS version 1.x. Nginx is used as a reverse proxy.

The data layer includes MongoDB, Redis, and MySQL with MaxMind data. Asynchronous communication is handled using RabbitMQ.

## Observability and Monitoring

All services are instrumented with Instana components to enable automatic distributed tracing and metrics collection. This provides end-to-end visibility across the entire application, including service latency, dependencies, and performance bottlenecks.

To view performance data and traces, an Instana account is required. A free trial account can be used for testing and learning purposes.

## Building the Application from Source

A recent version of Docker and Docker Compose is required to build the project from source. Configuration values such as image registry and version tags can be customized through the .env file.

To enable tracing for the Nginx service, an Instana agent key must be set as an environment variable before building the images.

The application images can be built using Docker Compose. If a custom image registry is configured, the images can also be pushed to that registry after the build process is complete.

## Running the Application Locally

The application can be executed locally using Docker Compose. If the images were not built from source, they can be pulled directly from Docker Hub.

Once started, the storefront becomes available through a local web browser. An optional configuration allows the application to run together with a load generation setup to simulate user traffic.

## Kubernetes Deployment

The project supports deployment to Kubernetes clusters using Helm charts. This allows the application to be deployed locally using Minikube or to cloud-based Kubernetes environments.

All container images are publicly available, making it possible to deploy the application without building images locally. Service access depends on the Kubernetes environment and may be exposed through a NodePort or load balancer.

## Load Generation

A separate load generation utility is included in the project. It is implemented in Python using Locust and is designed to simulate realistic user behavior against the application.

The load generator can be executed as a standalone container or deployed within a Kubernetes cluster. This component is useful for stress testing, performance analysis, and observability demonstrations.

## Prometheus Metrics

Selected services expose Prometheus-compatible metrics endpoints. These metrics provide insight into user behavior and transaction patterns within the application.

The cart service exposes counters related to items added to shopping carts. The payment service exposes counters and histograms related to completed purchases, cart sizes, and total cart values.

## Website and End User Monitoring

The frontend supports website and end-user monitoring through Instana. Configuration is handled through environment variables when using Docker Compose or through values defined in the Helm chart when deploying to Kubernetes.

No manual JavaScript injection is required, as monitoring is handled automatically by the application configuration.

## Conclusion

This project allowed me to gain practical experience with microservices architecture, containerization, Kubernetes deployment, and observability tooling. It serves as a solid foundation for demonstrating skills related to full stack development, cloud-native systems, and distributed application monitoring.

Author: Samuel Starling Vasquez

