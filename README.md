# CodeP Platform Configuration Files

This repository contains configuration files for the CodeP platform, used to demonstrate the initial and enhanced DevSecOps architectures as part of a PFE project. The files are organized into two directories: `pre-enforcement` and `post-enforcement`.

## Directory Structure

### pre-enforcement

Contains configuration files for the initial CodeP platform setup.

- `docker-compose.yml`: Defines services including Jenkins, Nexus, GitLab, SonarQube, and supporting services (PostgreSQL, Redis).
- `codepDockerfile.jenkins`: Dockerfile for a custom Jenkins image with SonarScanner and Node.js for build and analysis tasks.
- `Jenkinsfile`: Pipeline configuration for the `codep-test-project`, including build, SonarQube scan, and Nexus upload stages.

### post-enforcement

Contains configuration files for the enhanced CodeP platform with additional security and monitoring tools.

- `docker-compose.yml`: Enhanced setup with additional services: Keycloak, OpenLDAP, phpLDAPadmin, Prometheus, Grafana, and OWASP Threat Dragon.
- `codepDockerfile.jenkins`: Enhanced Dockerfile integrating security tools like OWASP Dependency-Check, OPA, Trivy, and GPG for artifact signing.

## Usage

These files are referenced in the PFE report to illustrate the evolution of the CodeP platform from its initial state to a security-enhanced DevSecOps architecture. Refer to the report for detailed context and explanations.

## Prerequisites

- Docker and Docker Compose for running `docker-compose.yml`.
- A project structure with Java and Node.js components for the `Jenkinsfile`.

## Setup

```bash
# Clone the repository
git clone https://github.com/username/codep-platform-configs

# Navigate to the desired directory
cd pre-enforcement   # or post-enforcement

# Start the services
docker-compose up -d
```

For pipeline execution, configure Jenkins with the provided Jenkinsfile and ensure connectivity to SonarQube and Nexus.

## Notes
- The Jenkinsfile assumes credentials (SONAR_AUTH_TOKEN, jenkins-nexus) are configured in Jenkins.
- The enhanced docker-compose.yml includes resource limits (e.g., memory, CPU) for some services; adjust as needed.
- For detailed setup instructions, refer to the “Mise en œuvre” section of the PFE report.
- Ensure network configurations (e.g., codep_network) are compatible with your environment.

## License
This project is for educational purposes as part of a PFE submission. No specific license is applied unless otherwise stated.
