# 🛡️ Wazuh SIEM & EDR Lab – Endpoint Security (Linux & Windows)

## 📌 Présentation du projet

Ce projet consiste à la mise en œuvre d’une plateforme complète de **supervision de la sécurité des systèmes d’information** basée sur **Wazuh**, combinant les approches :

- **SIEM (Security Information and Event Management)**
- **EDR (Endpoint Detection and Response)**

L’environnement est déployé sur **AWS Learner Lab** et intègre des endpoints **Linux** et **Windows**, simulant une infrastructure d’entreprise moderne supervisée par un SOC.

Ce dépôt regroupe l’ensemble des ressources du projet : documentation, configurations, captures d’écran et démonstrations de sécurité.

---

## 🎯 Objectifs pédagogiques

- Déployer une architecture SIEM/EDR dans le Cloud
- Superviser des endpoints Linux et Windows
- Centraliser et corréler les événements de sécurité
- Mettre en évidence les concepts de :
  - Endpoint Security
  - IAM / PAM
  - Threat Hunting
- Générer et analyser des alertes de sécurité réelles

---

## 🏗️ Architecture du lab

### Composants

- **Wazuh Server (Ubuntu 22.04)**
  - Wazuh Manager
  - Wazuh Indexer
  - Wazuh Dashboard (SIEM)

- **Client Linux (Ubuntu 22.04)**
  - Wazuh Agent

- **Client Windows (Windows Server)**
  - Wazuh Agent

### Flux réseau

| Service | Port | Description |
|------|------|------------|
| Agent communication | 1514/TCP | Logs et événements |
| Agent enrollment | 1515/TCP | Enrôlement |
| Dashboard | 443/TCP | Accès Web sécurisé |
| SSH | 22/TCP | Administration Linux |
| RDP | 3389/TCP | Administration Windows |

📸 **Capture à insérer ici**  
`screenshots/architecture.png`  
*(Schéma VPC + instances EC2 + Security Groups)*

---

## ☁️ Déploiement AWS

- Environnement : **AWS Learner Lab**
- Instances EC2 :
  - 1 × Ubuntu 22.04 (Wazuh Server)
  - 1 × Ubuntu 22.04 (Linux Client)
  - 1 × Windows Server (Windows Client)
- Toutes les instances sont déployées dans :
  - Le même VPC
  - Le même subnet
- Sécurité assurée par des **Security Groups restrictifs**

📄 Détails complets :  
👉 `installation/aws-setup.md`

---

## ⚙️ Installation de Wazuh

### Serveur Wazuh (All-in-One)

Installation automatisée incluant :
- Manager
- Indexer
- Dashboard

```bash
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh
sudo bash wazuh-install.sh -a
