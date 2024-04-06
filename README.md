
 # Session Management Function (SMF)
//===============================================================
Session Management Function (SMF) is a core component of 5G networks responsible for managing communication sessions between user equipment (UE) and the network.

# Overview
SMF facilitates session establishment, modification, and termination, ensuring seamless connectivity and efficient data transfer in 5G networks.

## Pipeline Stages:
### Verify Branch:

Displays the current Git branch being built.

### Login to Dockerhub:
Logs in to Dockerhub using stored credentials.

### Pulling base image from Dockerhub:
Pulls the latest base image from Dockerhub (abodiaa/smf-base:latest).

### Docker Build:
Lists Docker images. Builds a Docker image tagged as abodiaa/smf:latest. Lists Docker images again.

### Scan Image for Common Vulnerabilities and Exposures:
Scans the Docker image for common vulnerabilities and exposures using Trivy. Generates a JSON report of vulnerabilities.

### Pushing to Dockerhub:
Pushes the built Docker image (abodiaa/smf:latest) to Dockerhub.

### Build and Package Helm Chart:
Packages the Helm chart located in ./helm/.

### Configure Kubernetes Context:
Configures the Kubernetes context for AWS EKS cluster 5G-Core-Net.

### Deploy Helm Chart on EKS:
Upgrades or installs the Helm chart named nrf onto the EKS cluster.

## Post-build Actions:
Always:
Archives the Trivy vulnerability report. Removes Docker images (abodiaa/nrf:latest and abodiaa/smf-base:latest).