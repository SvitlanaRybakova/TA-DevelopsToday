# Error Logging Service Architecture Design

## Overview

The error logging service is designed to capture, process, store, and analyze application errors efficiently while providing developers with actionable insights through a web dashboard and real-time alerts. The architecture is modular, scalable, and optimized for performance, security, and ease of maintenance.

## Application Architecture

**Client SDK**
Integrated into client applications to capture and transmit error logs

1. Technology: TypeScript
2. Key features: TypeScript offers code reliability by static typing, automatic error capture, asynchronus functions and integration with the JavaScript ecosystem, especially when targeting web or Node.js environments

**API Backend**
Receives logs from the SDK, processes them, and stores them in the database. It also triggers alerts based on defined rules

1. Technology: Node.js with Express.js.
2. Key features: Node.js has a rich ecosystem, event-driven, non-blocking I/O, nativly support JSON, can be scaled using balancers and mutliple instances

**Database**
Stores the error log data

1. Technology: Supabase with PostrgeSQL
2. Key features: reliable data storage, real-time dashboard updates, has a integrated authentication and edge functions, scalability for growth, easy to integrate backend services

**Web Dashnoard**
Provides a user interface for developers to view, search, filter, and analyze the logged errors

1. Technology: React.js with UI library (Tailwind UI, Shadsn)
2. Key featueres: React based on js that a native browser language, has component-based architecture that provides reusability and maintability, has a better perfomance optimozation (updated virtual DOM), rich ecosystem, resposivenes.
   Shadcn UI is build on pot of Tailwind CSS, provides a set UI components that are prestyled, small component library that include just components in use, have a full controll over components strucutre and styling

**Alerting Service**
Monitors incoming logs and triggers notifications

1. Technology: RabbitMQ
2. Key features:RabbitMQ supports different routing messages like Direct exchange that based on exact routing key match (could be usefuk for sending specific errors). Fanout exchange cold be suitable sending every errorlog. Topic exchange where routes messages based on routing key pattern and headers echange that based on heasders rather that routing keys. RabbitMQ ensuring that a message is processed successfully, supports queues and message configuration

**DevOps**
Establish a CI/CD pipeline for automated building, testing, and deployment

1. Technology: Docker, Kubernetes, GitLab CI/CD or GitHub Actions, Elasticsearch

2. Key features:
   **Docker** for packaging applications and their dependencies
   **Kubernetes** for managing and scaling containerized applications.
   **CI/CD** GitLab CI/CD or GitHub Actions for automated building, testing, and deployment
   **Logging** Elasticsearch has a real-time analytics and monitorig (creating the dashboards in Kibana), support full-text search capabilities, can tore and manage large volumes of logs


![diagram-export-10-04-2025-21_35_54](https://github.com/user-attachments/assets/bc536eff-15ad-4fca-a809-c59daa062746)
