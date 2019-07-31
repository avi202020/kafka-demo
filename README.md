# RFP Demo

## Prerequisites

- Docker with Kubernetes (standard on Mac and Windows)
- helm
- terraform
- jq (for parsing kubectl responses)
- git (for getting Confluent helm charts)

## Installation

### Prep

1. Get your local Kube up and running
2. `terraform init terraform`
3. `make kube.proxy`

### Kube dashboard

1. `make dashboard.open`. This will open the web app and put the token in your clipboard
2. Use the token from your clipboard

### Provisioning

1. `make provision`

## Accessing services

### Control Center UI

1. `make control-center.open`

### Grafana

1. `make grafana.open`. User: admin, password is in your clipboard.

### Twitter forwarder

The Twitter forwarder is started by default, but you can also stop it.

1. `make twitter-forwarder.start` to start feeding Twitter messages to the database
2. `make twitter-forwarder.stop` to... stop

### Jenkins

1. Wait a few minutes for the service to come up
2. `make jenkins.open`
3. `make jenkins.password`
4. Log in with user admin and password from the output above

### Console consumer for Twitter feed

1. `make consumer.twitter`