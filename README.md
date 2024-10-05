# PiMetrics

## Prerequisites

Before we get started installing the stack, we need to make sure that the following prerequisites are met:
- Docker is installed on the host machine
- Docker Compose is installed on the host machine
- The host machine is running a Raspberry PI OS or any other compatible Linux distribution

## Installation and Configuration

To install the stack, follow the steps below:

- Clone this repository to your host machine.
```bash
git clone https://github.com/Ravi19967/PiMetrics.git
```

- Enter to the cloned directory.
```bash
cd PiMetrics
```

 - Create `data` directory and change the ownership of the `prometheus` and `grafana` folders for a nice and clean installation.
```bash
mkdir -p prometheus/data grafana/data && \
sudo chown -R 472:472 grafana/ && \
sudo chown -R 65534:65534 prometheus/
```

 - Start the stack with `docker-compose`.
```bash
docker-compose up -d
```

This will start all the containers and make them available on the host machine.
<br/>The following ports are used (only Grafana is exposed on the host machine):
- 3000: Grafana
- 9090: Prometheus
- 8080: cAdvisor
- 9100: NodeExporter