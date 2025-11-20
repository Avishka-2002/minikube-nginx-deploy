Here’s a clean, professional `README.md` file you can use for your GitHub repo, M.G. It’s modular, bilingual (Sinhala-English), and perfect for showcasing your Kubernetes + NGINX deployment project:

---

```markdown
# 🚀 Custom NGINX App Deployment with Kubernetes & Minikube

This project demonstrates how to build and deploy a custom HTML app using Docker, NGINX, and Kubernetes (Minikube). Ideal for learning container orchestration, DevOps workflows, and static site hosting.

---

## 📁 Project Structure

```
Mini_Cube_Practice/
├── app1-deployment.yaml
├── app1-service.yaml
├── myapp/
│   ├── index.html
│   └── Dockerfile
```

---

## 🧠 Workflow Summary – Sinhala-English

| Step | Command | Sinhala Explanation |
|------|---------|---------------------|
| 1️⃣ Delete old app2 | `kubectl delete deployment app2`<br>`kubectl delete service app2-service` | පරණ app එක delete කරනවා |
| 2️⃣ Create folder + HTML | `mkdir myapp && cd myapp`<br>`nano index.html` | HTML file එක add කරනවා |
| 3️⃣ Add Dockerfile | `nano Dockerfile` | NGINX + HTML එක bundle කරනවා |
| 4️⃣ Build image | `docker build -t my-nginx-app2 .` | Docker image එක build කරනවා |
| 5️⃣ Load to Minikube | `minikube image load my-nginx-app2` | Minikube එකට image එක push කරනවා |
| 6️⃣ Update deployment YAML | `nano app2-deployment.yaml` | Pod එක recreate කරන YAML |
| 7️⃣ Update service YAML | `nano app2-service.yaml` | Browser access port එක define කරනවා |
| 8️⃣ Apply YAMLs | `kubectl apply -f app2-deployment.yaml`<br>`kubectl apply -f app2-service.yaml` | Pod + service create කරනවා |
| 9️⃣ Access app | `minikube service app2-service` | Browser එකෙන් app එක access කරනවා |

---

## 🔧 Technologies Used

- Docker 🐳
- Kubernetes (Minikube) ☸️
- NGINX 🌐
- YAML + CLI workflows
- WSL + Linux + Git

---

## 🌍 Live Access (Local)

After deployment, access your app via:

```bash
minikube service app2-service
```

Example URL: `http://127.0.0.1:31338`

