# Monitoring Stack

This project sets up a monitoring stack using Docker Compose. The stack includes Prometheus, Grafana, Loki, Fluent Bit, and OpenTelemetry Collector.

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Accessing the Services](#accessing-the-services)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Overview

This monitoring stack allows you to collect, store, and visualize metrics and logs from your applications. The stack includes the following components:

- **Prometheus**: Collects and stores metrics.
- **Grafana**: Visualizes metrics and logs.
- **Loki**: Collects and stores logs.
- **Fluent Bit**: Collects and forwards logs.
- **OpenTelemetry Collector**: Collects and forwards metrics and traces.

## Prerequisites

Before you begin, ensure you have the following installed:

- Docker
- Docker Compose

## Installation

1. Clone this repository:

    ```sh
    git clone <repository-url>
    cd <repository-directory>
    ```

2. Create or modify the configuration files as needed (e.g., `loki-config.yaml`).

3. Start the stack:

    ```sh
    docker-compose up -d
    ```

## Configuration

- **Prometheus**: Configuration can be modified in `prometheus.yml`.
- **Grafana**: Configuration can be modified in `grafana.ini` or via the Grafana web UI.
- **Loki**: Configuration can be modified in `loki-config.yaml`.
- **Fluent Bit**: Configuration can be modified in `fluent-bit.conf`.
- **OpenTelemetry Collector**: Configuration can be modified in `otel-config.yaml`.

## Usage

### Adding Grafana Data Sources

1. Access Grafana at [http://localhost:3001](http://localhost:3001).
2. Log in with the default credentials (`admin` / `admin`).
3. Go to **Configuration** -> **Data Sources** -> **Add data source**.
4. Select **Loki**.
5. Set the URL to `http://loki:3100`.
6. Click **Save & Test**.

### Creating Dashboards

1. In Grafana, go to **Create** -> **Dashboard**.
2. Add panels to visualize metrics from Prometheus and logs from Loki.

## Accessing the Services

- **Grafana**: [http://localhost:3001](http://localhost:3001)
- **Prometheus**: [http://localhost:9090](http://localhost:9090)
- **Loki**: No direct web UI, but accessible via Grafana.
- **Fluent Bit**: Logs can be configured to be forwarded to Loki.
- **OpenTelemetry Collector**: Configured to collect and forward metrics and traces.

## Troubleshooting

If you encounter any issues, check the logs of the respective services:

```sh
docker-compose logs <service_name>
