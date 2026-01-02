# 🛡️ Wazuh SIEM & EDR Lab – Sécurité des Endpoints (Linux & Windows)

## 📌 Présentation du projet

Ce projet présente la mise en œuvre d’une plateforme complète de **supervision et de protection de la sécurité des systèmes d’information**, basée sur **Wazuh**, combinant les approches **SIEM** et **EDR**.

L’infrastructure est déployée sur **AWS Learner Lab** et intègre des endpoints **Linux** et **Windows**, simulant un environnement d’entreprise moderne supervisé par un **SOC (Security Operations Center)**.

---

## 🎯 Objectifs du projet

- Déployer une architecture SIEM/EDR fonctionnelle dans le Cloud
- Superviser des endpoints Linux et Windows
- Centraliser et analyser les événements de sécurité
- Illustrer les concepts de Endpoint Security, IAM/PAM et Threat Hunting
- Générer et analyser des alertes de sécurité réelles

---

## 🏗️ Architecture globale du lab

### Composants
- Wazuh Server (Ubuntu 22.04)
- Client Linux (Ubuntu 22.04)
- Client Windows (Windows Server)

📸 **Capture à insérer ici : Schéma VPC + EC2 + Security Groups**
<img width="2816" height="1536" alt="Gemini_Generated_Image_w4it79w4it79w4it" src="https://github.com/user-attachments/assets/159a707c-cc60-4166-a1f8-61674a3f5cb0" />

---

## 🌐 Flux réseau

| Service | Port | Description |
|------|------|------------|
| Agent communication | 1514/TCP | Logs vers Wazuh |
| Agent enrollment | 1515/TCP | Enrôlement |
| Dashboard | 443/TCP | Accès Web |
| SSH | 22/TCP | Admin Linux |
| RDP | 3389/TCP | Admin Windows |

---

## ⚙️ Installation de Wazuh

```bash
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh
sudo bash wazuh-install.sh -a
```

📸 **Capture à insérer ici : Wazuh Dashboard**

---

## 🧩 Déploiement des agents

- Agent Linux via Dashboard
- Agent Windows via PowerShell

📸 **Capture à insérer ici : Agents actifs**

---

## 🚨 Démonstrations SIEM & EDR

### Linux
- SSH brute force
- Sudo
- File Integrity Monitoring

📸 **Capture à insérer ici : Alertes Linux**

### Windows
- Failed logon (4625)
- Création utilisateur
- Ajout au groupe Administrators

📸 **Capture à insérer ici : Alertes Windows**

---

## 🔎 Analyse sécurité

- SIEM : centralisation et corrélation
- EDR : surveillance endpoint
- IAM/PAM : contrôle des accès

---

## 🏁 Conclusion

Ce projet démontre la mise en œuvre d’un SOC moderne basé sur Wazuh, dans un environnement Cloud réaliste.

---

## 👤 Auteur
**Marwane Mounir**
