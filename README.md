============================
Kubernetes Web Application Practicals
============================

This repository contains Kubernetes manifests to deploy a web application.

---

============================
1. Pod Manifest
============================

Overview:
Deploys a single pod running the web application.

Key Concepts:
- Pod as the smallest deployable unit in Kubernetes
- Encapsulates the container(s) and resources needed
- Supports labels and selectors for service discovery

Advantages:
- Simple and lightweight deployment
- Good for testing or single-instance apps
- Helps understand basic pod structure

File:
- k8s-pod-manifest.yml – Pod manifest for the web application

Usage:
Deploy the pod using:
$ kubectl apply -f k8s-pod-manifest.yml
$ kubectl get pods
$ kubectl logs <pod-name>

---

============================
2. Service Manifest
============================

Overview:
Exposes the web application pod internally or externally using a Service.

Key Concepts:
- ClusterIP, NodePort, LoadBalancer types
- Provides stable IP and DNS for pods
- Allows communication between pods or external access

Advantages:
- Abstracts pod IPs for reliable access
- Load balances traffic to multiple pods (if scaled)
- Enables external access for web applications

Files:
- k8s-service-manifest.yml – Service manifest
- k8s-pod-service-manifest.yml – Optional pod + service combined manifest

Usage:
Deploy the service using:
$ kubectl apply -f k8s-service-manifest.yml
$ kubectl apply -f k8s-pod-service-manifest.yml
$ kubectl get svc

---

============================
3. Namespace (Optional)
============================

Overview:
Organizes resources under a specific namespace.

File:
- sravan-ns.yml – Namespace manifest

Usage:
Create the namespace using:
$ kubectl apply -f sravan-ns.yml
$ kubectl get ns

---

References:
- Kubernetes Pods: https://kubernetes.io/docs/concepts/workloads/pods/
- Kubernetes Services: https://kubernetes.io/docs/concepts/services-networking/service/
- Kubernetes Namespaces: https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/
