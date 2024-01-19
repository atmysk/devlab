# DevOps Management Platform Documentation

## Table of Contents

1. [Introduction](#1-introduction)
2. [Prerequisites](#2-prerequisites)
3. [Setting Up Auth0](#3-setting-up-auth0)
4. [Configuring MongoDB](#4-configuring-mongodb)
5. [Local Development](#5-local-development)
   - [Running the Application Locally](#running-the-application-locally)
   - [Accessing the Dev Environment](#accessing-the-dev-environment)
6. [Continuous Integration and Deployment](#6-continuous-integration-and-deployment)
   - [GitHub Actions Workflow](#github-actions-workflow)
   - [Deployment to Kubernetes](#deployment-to-kubernetes)
7. [Monitoring and Logging](#7-monitoring-and-logging)
   - [Prometheus and Grafana](#prometheus-and-grafana)
   - [Centralized Logging](#centralized-logging)
8. [Scaling and Cloud Integration](#8-scaling-and-cloud-integration)
   - [Horizontal Pod Autoscaler (HPA)](#horizontal-pod-autoscaler-hpa)
   - [Cloud Provider Integration (AWS EKS)](#cloud-provider-integration-aws-eks)
9. [Conclusion](#9-conclusion)
10. [Appendix](#10-appendix)

## 1. Introduction

This documentation provides a step-by-step guide on setting up and using the DevOps management platform. The platform includes a full-stack application with OAuth authentication, React UI, Express server, Docker, Kubernetes, Helm, monitoring with Prometheus and Grafana, and cloud-based MongoDB.

## 2. Prerequisites

Before starting, ensure that you have the following prerequisites:

- [Node.js](https://nodejs.org/) installed
- [Docker](https://www.docker.com/) installed
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) installed for Kubernetes deployment
- [Helm](https://helm.sh/docs/intro/install/) installed for Helm chart management
- [AWS CLI](https://aws.amazon.com/cli/) installed for cloud provider integration

## 3. Setting Up Auth0

1. Create an account on [Auth0](https://auth0.com/) if you don't have one.
2. Set up a new application in Auth0 and note down the client ID, client secret, and domain.
3. Update the `.env` file in the root directory with Auth0 configuration.

```env
REACT_APP_API_URL=http://localhost:3001
AUTH0_DOMAIN=your-auth0-domain
AUTH0_CLIENT_ID=your-client-id
AUTH0_CLIENT_SECRET=your-client-secret
```

## 4. Configuring MongoDB

1. Install [MongoDB](https://www.mongodb.com/try/download/community) locally or use a cloud-based service like MongoDB Atlas.
2. Update the `.env` file with the MongoDB connection string.

```env
MONGODB_CONNECTION_STRING=your-mongodb-connection-string
```

## 5. Local Development

### Running the Application Locally

```bash
cd code-display-app
npm install
npm start
```

### Accessing the Dev Environment

- Frontend: http://localhost:3000
- Backend: http://localhost:3001

## 6. Continuous Integration and Deployment

### GitHub Actions Workflow

Refer to the [GitHub Actions Workflow](.github/workflows/main.yml) for CI/CD configuration.

### Deployment to Kubernetes

1. Install [Minikube](https://minikube.sigs.k8s.io/docs/start/) or use a cloud-based Kubernetes cluster.
2. Deploy the Helm chart:

```bash
helm install my-code-display-app ./helm-chart
```

## 7. Monitoring and Logging

### Prometheus and Grafana

Access Prometheus: http://localhost:9090
Access Grafana: http://localhost:80 (credentials: admin/admin)

### Centralized Logging

Use Fluentd and Elasticsearch for centralized logging.

## 8. Scaling and Cloud Integration

### Horizontal Pod Autoscaler (HPA)

Update the `hpa.yaml` file in the Helm chart with your desired configurations.

### Cloud Provider Integration (AWS EKS)

Update the `eks-cluster.yaml` file with your AWS region and node group settings.

## 9. Conclusion

You have successfully set up the DevOps management platform. Customize configurations based on your business needs and scale as required.

## 10. Appendix

- [Kubernetes Documentation](https://kubernetes.io/docs/home/)
- [Helm Documentation](https://helm.sh/docs/)
- [Prometheus Documentation](https://prometheus.io/docs/introduction/overview/)
- [Grafana Documentation](https://grafana.com/docs/grafana/latest/)
- [Fluentd Documentation](https://docs.fluentd.org/)
- [Elasticsearch Documentation](https://www.elastic.co/guide/index.html)
- [AWS EKS Documentation](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html)

Feel free to enhance this documentation based on specific use cases or additional features you incorporate into the platform.
