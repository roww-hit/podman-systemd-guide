# 🐳 Running Podman Containers as Systemd Services

![Podman](https://img.shields.io/badge/Podman-892CA0?style=for-the-badge&logo=podman&logoColor=white)
![Systemd](https://img.shields.io/badge/Systemd-Target-green?style=for-the-badge&logo=systemd&logoColor=white)
![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white)

> A step-by-step guide to managing Podman containers using the Systemd initialization system. This ensures containers start automatically on boot and behave like standard system services.

---

## 📋 Table of Contents
- [Prerequisites](#-prerequisites)
- [Workflow Diagram](#-workflow-diagram)
- [Installation Guide](#-installation-guide)
- [Managing the Service](#-managing-the-service)
- [Logging & Debugging](#-logging--debugging)
- [Use Cases](#-use-cases)

---

## 🛠 Prerequisites

Before beginning, ensure Podman is installed. 

**Important:** For rootless containers to start on boot without the user being logged in, you must enable "lingering":

```bash
loginctl enable-linger $USER
