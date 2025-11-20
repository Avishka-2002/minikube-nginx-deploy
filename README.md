# 🚀 Custom NGINX Application Deployment with Kubernetes & Minikube

This repository documents and provides the configuration files for deploying a custom static HTML application using **NGINX**, packaged with **Docker**, and orchestrated via **Kubernetes (Minikube)**.

This project serves as an excellent foundational example for mastering essential DevOps concepts, including containerization, local cluster management, and Infrastructure as Code (IaC) with YAML.

---

## 💡 Key Project Components

| File/Directory | Description | Purpose |
| :--- | :--- | :--- |
| `app-deployment.yaml` | Kubernetes Deployment Manifest | Defines the desired state (e.g., image, replica count) for the application Pods. |
| `app-service.yaml` | Kubernetes Service Manifest | Defines how to expose the application (LoadBalancer or NodePort) for external access. |
| `myapp/index.html` | Application Source Code | The static content served by the NGINX web server. |
| `myapp/Dockerfile` | Docker Build Instructions | Specifies the base image (NGINX) and copies the HTML content into the container. |

---

## ⚙️ Deployment Workflow

The following steps summarize the end-to-end process from source code to live application within the Minikube environment:

### 1. Application Containerization (Docker)
1.  **Create Source Files:** Define the HTML content (`myapp/index.html`) and the container configuration (`myapp/Dockerfile`).
2.  **Build Docker Image:** Build the custom NGINX image locally.
    ```bash
    docker build -t my-nginx-app .
    ```

### 2. Minikube Integration
3.  **Load Image to Minikube:** Push the newly built image directly into the Minikube cluster's local registry. This bypasses the need for an external registry (like Docker Hub) for local testing.
    ```bash
    minikube image load my-nginx-app
    ```

### 3. Kubernetes Deployment (IaC)
4.  **Define Resources:** Ensure the `app-deployment.yaml` and `app-service.yaml` files reference the correct image name (`my-nginx-app`) and desired ports.
5.  **Apply Manifests:** Apply the YAML files to create the Pods and Service resources in the cluster.
    ```bash
    kubectl apply -f app-deployment.yaml
    kubectl apply -f app-service.yaml
    ```

### 4. Verification and Access
6.  **Verify Deployment:** Confirm the Pods and Service are running correctly.
    ```bash
    kubectl get all
    ```
7.  **Access Application:** Use Minikube to automatically open the exposed Service in your browser.
    ```bash
    minikube service app-service
    ```
    *(The service name should match the name defined in your `app-service.yaml`)*

---

## 🛠️ Technologies & Tools

* **Containerization:** Docker 🐳
* **Orchestration:** Kubernetes (Minikube) ☸️
* **Web Server:** NGINX 🌐
* **Methodology:** Infrastructure as Code (IaC), CLI Workflows
* **Environment:** WSL / Linux

---
