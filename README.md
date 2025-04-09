# 🚀 Dockerized Web App Deployment Guide

A complete step-by-step guide to deploying a **Dockerized web application** on a **virtual server (VPS or VDS)**. This guide walks you through configuring your server, setting up Docker, managing networking with Nginx, securing your deployment with HTTPS, and applying essential security practices.

Whether you're deploying a simple site or a production-grade web service, this guide will help you get your app live with full control over the infrastructure.

---

## 📚 Table of Contents

1. [Introduction](#introduction)
2. [What You'll Learn](#what-youll-learn)
3. [Guide Parts](#guide-parts)
4. [Who Is This For?](#who-is-this-for)
5. [License](#license)

---

## 🧭 Introduction

Deploying an app on a virtual machine can be intimidating — especially when you want complete control using Docker, without relying on a platform-as-a-service. This guide provides a **modular, practical approach** for going from a fresh server to a live, secure, and scalable deployment.

---

## 🎯 What You'll Learn

- How to prepare and secure a fresh virtual server
- How to install and use Docker and Docker Compose
- How to configure Nginx as a reverse proxy
- How to enable HTTPS with Let's Encrypt
- How to apply basic server hardening and firewall rules

---

## 🧱 Guide Parts

| Part | Description |
|------|-------------|
| [Part 1](./part1-server-setup.md) | Server Initial Configuration (users, SSH, updates) |
| [Part 2](./part2-docker-app.md) | Docker & Docker Compose setup |
| [Part 3](./part3-nginx-network.md) | Nginx setup and reverse proxy config |
| [Part 4](./part4-ssl-certificates.md) | SSL setup with Let's Encrypt (Certbot) |
| [Part 5](./part5-security.md) | Security precautions: UFW, SSH, Fail2Ban |

---

## 👤 Who Is This For?

- Developers deploying their own apps on cloud servers
- Teams building internal deployment infrastructure
- Anyone who wants to learn real-world, server-side Docker deployment

---

## 📄 License

MIT License – feel free to fork, use, and contribute.

---

## 🐧 Built for Linux-based servers
