# Enterprise GitOps CI/CD Pipeline with Jenkins & Argo CD

This is the complimentary repository for the deployment of the [Score Board Application](https://github.com/taofeekaoyusuf/score-board-app.git) showcasing a complete modern GitOps software delivery pipeline. Source code changes trigger an automated build and security checking workflow, culminating in automated, zero-touch Kubernetes deployments via declarative desired-state configuration syncing.

## SCOREBOARD APPLICATION

#### This is an application to record the scores of any game being played by two Opponents.

<img width="3024" height="1612" alt="image" src="https://github.com/user-attachments/assets/0951d038-0e90-42fd-8520-1a6377caafca" />

## Architecture Flow

1. Jenkins dynamically edits the Kubernetes manifest repository (`gitops-repo`), tracking the precise application version tag.
2. **Argo CD** identifies a delta between the live cluster state and git desired state, initiating an automated rolling sync into the Kubernetes Cluster.

## Tech Stack Used

* **Declarative GitOps Engine**: Argo CD
* **Target Runtime Platform**: Kubernetes

## Prerequisites & Dependencies

To execute this architecture locally or on a cloud platform, verify the installation of:
* **Docker Engine** (v20.10+)
* **Minikube** or **Kind** (Kubernetes Cluster v1.26+)
* **Jenkins Server** with standard plugins installed:
  * SonarQube Scanner
  * Pipeline: Stage View
  * Docker Pipeline
  * Credentials Binding
* **Argo CD** installed on your cluster:
  ```bash
  kubectl create namespace argocd
  kubectl apply -n argocd -f [https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml](https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml)

This application can be forked and modified as pleased for more robustness.

@Copyright: TAOY