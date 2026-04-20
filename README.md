# 📱 Mobile Banking Kubernetes Deployment

This project contains Kubernetes manifests to deploy a **Mobile Banking application** using a Deployment and expose it via a Service.

---

## 🚀 Components

### 🔹 Deployment: `mobilebanking-rs`

* Runs **10 replicas** of the application
* Uses Docker image: `vickydockek11/ib-image:latest`
* Label: `app=bank`

### 🔹 Service: `mobilebankingservice`

* Type: `LoadBalancer`
* Exposes the application externally
* Routes traffic to pods with label `app=bank`

---

## 📂 Files

* `deployment.yaml` → Contains Deployment + Service configuration

---

## ⚙️ Prerequisites

* Kubernetes cluster (EKS / Minikube / Kops)
* `kubectl` installed and configured
* Docker image available in DockerHub

---

## 📦 Deployment Steps

### 1️⃣ Clone the repository

```bash
git clone <your-repo-url>
cd <repo-name>
```

### 2️⃣ Apply Kubernetes manifests

```bash
kubectl apply -f deployment.yaml
```

### 3️⃣ Verify resources

```bash
kubectl get pods
kubectl get svc
```

---

## 🌐 Access Application

Get external IP:

```bash
kubectl get svc mobilebankingservice
```

Then access:

```
http://<EXTERNAL-IP>
```

---

## 🔄 Scaling

To scale the application:

```bash
kubectl scale deployment mobilebanking-rs --replicas=20
```

---

## 🧹 Cleanup

```bash
kubectl delete -f deployment.yaml
```

---

