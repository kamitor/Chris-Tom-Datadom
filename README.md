# 🏰💾 **Chris & Tom Datadom** 🧀📡  
*Because the best hosting is built on knowledge, community, and a tiny bit of Dutch stubbornness.*  

![Chris & Tom Datadom Banner](https://via.placeholder.com/1200x400?text=Chris+%26+Tom+Datadom)  

## 🌍 **What is Chris & Tom Datadom?**  
Welcome to **Chris & Tom Datadom**, a self-hosted server project running in an environment where **redundancy meets reliability**, and where data is handled with the same care as a **perfectly wired rack**.  

We believe in **learning by doing**, **sharing knowledge**, and most importantly—**keeping things running, no matter what**. Whether it's an experiment, a playground for open-source tech, or a fortress of uptime, we've got it covered.  

---

## 🏗️ **What’s Inside the Datadom?**  

🖥️ **Self-hosted everything** – Because trusting a cloud is nice, but **being the cloud** is better.  
🔧 **Built on FOSS** – Proprietary software? Laat maar zitten.  
🛡️ **Secure & stable** – Just like that well-documented firewall rule.  
📡 **Network-first mindset** – Routes optimized, packets respected.  
🤖 **Automation & monitoring** – Because **efficiency > repetition**.  

---

## 🚀 **Why Chris & Tom Datadom?**  

✅ **Built with knowledge & community in mind**  
Chris & Tom Datadom isn’t just another self-hosted project—it’s an infrastructure designed to **enable learning, collaboration, and real-world experimentation**. Inspired by **VCH-Infra**, we believe that the best way to push innovation forward is to **make powerful tools accessible, document them well, and share knowledge freely**.  

✅ **A research-grade modular infrastructure**  
Much like **VCH-Infra**, this ecosystem is designed to **streamline research, development, and hosting**, integrating a mix of **virtualization, data analysis, automation, and security tools**. Every component is modular, open-source, and **built to support real-world applications**, whether for **academia, network engineering, or tech-driven research**.  

✅ **Carefully managed infrastructure, not just thrown together**  
Some people spin up a server and hope for the best. We **plan, optimize, and iterate**.  
- **Containerized everything** with Docker and Kubernetes for **scalability**.  
- **Automated provisioning** using Ansible to **reduce manual workload**.  
- **Real-time monitoring** with Grafana & Prometheus to **catch issues before they escalate**.  
- **Modular networking setup**, integrating BGP and VPNs for **secure and flexible access**.  

✅ **Reliability that won't ghost you at 2 AM**  
The best infrastructure is the one that **doesn’t need late-night intervention**. That’s why we **design for uptime and resilience** from day one:  
- **Load balancing & failover strategies** to keep services running.  
- **Automated alerts** for rapid troubleshooting.  
- **Version-controlled deployments** to prevent configuration drift.  

🔍 **We like to say:**  
*"If you can document it, you can improve it. If you can automate it, even better. If you don’t need to wake up for it, you’ve done it right."*  

---

## 🏗️ **How Does It Work?**  

### 🛠 **Centralized Tools & Pre-Configured Infrastructure**  
✅ **Seamless Access:** Everything is accessible via a **unified interface** with Traefik handling subdomain routing.  
✅ **Pre-Configured Services:** No need to spend **hours setting up**—we’ve done the hard work.  
✅ **Optimized for Research & Innovation:** **Graph data (Neo4j), AI experiments (OpenWebUI), workflow automation (n8n)** all in one ecosystem.  

### 🤝 **Collaboration at Its Core**  
✅ **Mattermost & Nextcloud** for real-time communication & secure file sharing.  
✅ **WorkAdventure** for virtual collaboration & knowledge-sharing.  
✅ **Gitea & Drone CI** for open-source development workflows.  

### 📊 **Data-Driven Insights & Observability**  
✅ **Prometheus & Grafana** monitor **infrastructure health** in real-time.  
✅ **Quant & Streamlit** for advanced analytics & visualization.  
✅ **BGPalerter & Bird** for **network intelligence & routing management**.  

---

## 🛡️ **Is It Secure & Scalable?**  

🔒 **Security & Compliance:**  
- **Encrypted backups** with Restic & BorgBackup.  
- **Role-based access control (RBAC)** & **2FA enforcement** for all critical services.  
- **GDPR-compliant tools** for data privacy & regulatory compliance.  

📈 **Scalability & Performance:**  
- **Dockerized architecture** for rapid scaling.  
- **Cloud-native storage solutions** to accommodate **growing research data**.  
- **Automated monitoring** to ensure the system **adapts as usage increases**.  

---

## 🎯 **What's in It for You?**  

### 🏆 **Streamlined Research & Operations**  
- No more **fragmented toolsets**—everything integrates seamlessly.  
- Designed to **cut setup times & eliminate configuration headaches**.  

### 💰 **Cost-Efficient & Open-Source**  
- No **licensing fees** or vendor lock-in.  
- Built entirely on **FOSS tools trusted by industry leaders**.  

### 🌍 **Real-World Impact & Innovation**  
- Enables **cutting-edge research in supply chain finance** & **network automation**.  
- Bridges the gap between **academic research & industry applications**.  
- Provides **students & researchers with production-grade tools**.  

---

# 🏗️ Chris & Tom Datadom - Technical Architecture Overview  

## 📜 Overview  
Chris & Tom Datadom is a **containerized, modular infrastructure** designed for **secure, scalable, and research-friendly hosting**. It integrates key components for **networking, security, monitoring, data management, and automation** while maintaining **high availability and failover support**.

```mermaid
graph TD;
    
    %% Networking & Routing
    A1[🌍 Traefik (Reverse Proxy)] -->|Routes Traffic| B1[🖥️ Docker & Kubernetes]
    A2[🔐 WireGuard (VPN)] -->|Secures Access| A1
    A3[📡 Bird & BGPalerter (BGP Routing)] -->|Monitors Network| A1

    %% Security & Authentication
    S1[🔑 Keycloak (SSO & RBAC)] -->|Authenticates Users| A1
    S2[🔒 Vaultwarden (Secrets Management)] -->|Stores Secrets| S1

    %% Infrastructure & Compute
    B1 -->|Manages VMs & Containers| B2[🖥️ Proxmox VE (VMs & LXC)]
    B1 -->|Manages Containers| B3[🔧 Portainer (Docker Management)]
    
    %% Storage & Backup
    B4[💾 Nextcloud (File Sharing)] -->|Stores Data| B5[💾 Restic & BorgBackup (Backups)]

    %% Monitoring & Observability
    M1[📊 Prometheus (Metrics Collection)] -->|Feeds Data| M2[📈 Grafana (Visualization)]
    M1 -->|Monitors| M3[🚨 Zabbix (Alerting)]
    
    %% Collaboration & Development
    C1[💬 Mattermost (Team Chat)] -->|Integrates with| C2[📜 Gitea (Git Repositories)]
    C2 -->|Triggers Builds| C3[⚙️ Drone CI (CI/CD Automation)]

    %% Connections Between Components
    A1 -->|Routes Requests| B4
    A1 -->|Routes Requests| C1
    B1 -->|Supports Compute| C2
    B4 -->|Stores Research Data| C1
    M2 -->|Sends Alerts| C1
```

---

## 🌐 Networking & Routing Layer  
- **Traefik** – Acts as the main **reverse proxy**, handling SSL termination, subdomain routing, and load balancing.  
- **WireGuard** – Provides secure VPN access for admins and users requiring private network access.  
- **Bird & BGPalerter** – Manages **BGP routing** and alerts for network anomalies.  

**🔀 Flow:**  
1. Incoming requests hit **Traefik**, which directs traffic based on predefined **routing rules**.  
2. If a service requires VPN access, **WireGuard tunnels** are used.  
3. External traffic routing is **monitored & optimized** via **Bird & BGPalerter**.  

---

## 🔐 Security & Authentication Layer  
- **Keycloak** – Provides **SSO authentication, OAuth, and RBAC**.  
- **Vaultwarden** – Manages **secrets and credentials** for infrastructure security.  
- **2FA Enforcement** – Enabled for admin & sensitive services.  

**🔀 Flow:**  
1. Users authenticate via **Keycloak** (OAuth, SAML, or LDAP).  
2. Role-Based Access Control (RBAC) ensures **least privilege access**.  
3. Secrets (API keys, credentials) are stored in **Vaultwarden**.  

---

## 📡 Infrastructure & Compute Layer  
- **Proxmox VE** – Manages **VMs and LXC containers** for high-efficiency workloads.  
- **Docker & Kubernetes** – Used for **container orchestration** and service deployment.  
- **Portainer** – Provides a **web UI for managing Docker containers**.  

**🔀 Flow:**  
1. Virtual machines and containers are deployed via **Proxmox**.  
2. Containers run within **Docker/Kubernetes**, managed via **Portainer**.  
3. **Traefik routes** requests to the correct **containers/VMs**.  

---

## 💾 Storage & Backup Layer  
- **Nextcloud** – Provides **self-hosted file sharing & collaboration**.  
- **Restic & BorgBackup** – Automated, **encrypted backups** for data security.  

**🔀 Flow:**  
1. Data stored in **Nextcloud** for secure sharing.  
2. Scheduled **incremental backups** handled via **Restic & BorgBackup**.  
3. Off-site backups ensure **disaster recovery** capability.  

---

## 📊 Monitoring & Observability Layer  
- **Prometheus** – Collects **metrics from infrastructure components**.  
- **Grafana** – Provides **real-time visualization & dashboards**.  
- **Zabbix** – Enterprise-grade monitoring & alerts for **server health**.  

**🔀 Flow:**  
1. **Prometheus scrapes metrics** from all active services.  
2. **Grafana visualizes data** for insights into server health & network performance.  
3. **Zabbix provides alerts** for anomalies & failures.  

---

## 🤝 Collaboration & Development Layer  
- **Mattermost** – Self-hosted, secure messaging & team collaboration.  
- **Gitea** – Lightweight, self-hosted **Git repository service**.  
- **Drone CI** – **CI/CD automation** for software deployment.  

**🔀 Flow:**  
1. Developers push code to **Gitea**, triggering **Drone CI** pipelines.  
2. Teams communicate through **Mattermost**.  
3. Automated builds & deployments are managed through **Drone CI**.  

---

## **📜 Summary: End-to-End Workflow**  
1️⃣ **A request** enters through **Traefik**, determining **public/private access**.  
2️⃣ **Users authenticate** via **Keycloak** for **SSO & RBAC enforcement**.  
3️⃣ **Traffic is routed** to the correct **VM, container, or service**.  
4️⃣ **Compute resources** (Proxmox, Docker, Kubernetes) process the request.  
5️⃣ **Storage & backups** are securely managed via **Nextcloud & BorgBackup**.  
6️⃣ **Monitoring & alerts** via **Prometheus, Grafana, Zabbix** ensure system health.  
7️⃣ **Collaboration & development** tools (Mattermost, Gitea, Drone CI) support workflow.  

---

🔌 **Chris & Tom Datadom – A Secure, Scalable, and Open Research Infrastructure.** 🚀



## 🌍 **Real-World Examples & Inspiration**  

### **Brightlands Institute for Supply Chain Innovation (BISCI)**  
- **Location:** Maastricht University, Netherlands.  
- **Overview:** BISCI develops **smart & sustainable supply chain innovations** by applying the latest research to real-world challenges.  

### **Supply Chain Finance Barometer (PwC & SCF Community)**  
- **Findings:** Provides deep insights into **the evolution of supply chain finance**, identifying key drivers, challenges, and success factors.  

### **European Open Science Cloud (EOSC)**  
- **Initiative:** A European Commission effort to build an **integrated research infrastructure** that promotes open science and data sharing.  

---

## 💡 **Why Does This Matter?**  

Academic and research institutions face significant challenges:  
❌ **Fragmented tools** leading to inefficiencies.  
❌ **High licensing costs** for essential software.  
❌ **Lack of scalable infrastructure** that meets evolving research demands.  

Chris & Tom Datadom is built to **solve these challenges** by providing:  
✅ **A fully integrated, open-source ecosystem**.  
✅ **Pre-configured, scalable, and research-ready tools**.  
✅ **A sustainable, cost-efficient, and modular infrastructure**.  

📢 **We believe in making powerful infrastructure accessible, scalable, and open to those who need it most.** 🚀  

---

## 📜 **Roadmap**  

✔️ **Deploy core services & test resiliency** 🛠️  
✔️ **Ensure solid networking & failover strategies** 📡  
🚧 **Fine-tune automation & monitoring** 🤖  
🚧 **Share insights & best practices with the community** 💡  
🚧 **Expand functionality while keeping things **lean & efficient** 🏗️  

---

## 🏰 **Join the Datadom!**  

Want to contribute, collaborate, or just debate **the best way to structure VLANs?**  
We're always happy to **share insights**, **exchange ideas**, and **keep things running smoothly**.  

🔌 **Chris & Tom Datadom – Built for those who care about their infrastructure.**  



| **Tool**          | **Purpose**                                      | **GitHub** |
|-------------------|-------------------------------------------------|-----------|
| **Proxmox VE**   | Virtualization & container management           | [🔗 Proxmox](https://github.com/proxmox) |
| **Ansible**      | Automated server provisioning & configuration   | [🔗 Ansible](https://github.com/ansible/ansible) |
| **Docker**       | Containerized application deployment            | [🔗 Docker](https://github.com/moby/moby) |
| **Portainer**    | Web-based UI for managing Docker & Kubernetes   | [🔗 Portainer](https://github.com/portainer/portainer) |
| **Grafana**      | Monitoring & visualization for infrastructure   | [🔗 Grafana](https://github.com/grafana/grafana) |
| **Prometheus**   | Time-series database for metrics & alerting     | [🔗 Prometheus](https://github.com/prometheus/prometheus) |
| **Zabbix**       | Enterprise-grade monitoring solution            | [🔗 Zabbix](https://github.com/zabbix/zabbix) |
| **WireGuard**    | Fast, modern VPN for secure networking          | [🔗 WireGuard](https://github.com/WireGuard) |
| **BGPalerter**   | Monitoring & alerting for BGP network changes  | [🔗 BGPalerter](https://github.com/nttgin/BGPalerter) |
| **Bird**         | Open-source BGP routing daemon                  | [🔗 Bird](https://github.com/BIRD/bird) |
| **Vaultwarden**  | Self-hosted password management                 | [🔗 Vaultwarden](https://github.com/dani-garcia/vaultwarden) |
| **Keycloak**     | Identity & access management                    | [🔗 Keycloak](https://github.com/keycloak/keycloak) |
| **Nextcloud**    | Self-hosted cloud storage & collaboration       | [🔗 Nextcloud](https://github.com/nextcloud/server) |
| **Gitea**        | Self-hosted Git repository service              | [🔗 Gitea](https://github.com/go-gitea/gitea) |
| **Caddy**        | Automated HTTPS & reverse proxy                 | [🔗 Caddy](https://github.com/caddyserver/caddy) |
| **Traefik**      | Cloud-native reverse proxy & load balancer      | [🔗 Traefik](https://github.com/traefik/traefik) |
| **Pi-hole**      | Network-wide ad blocking & DNS filtering        | [🔗 Pi-hole](https://github.com/pi-hole/pi-hole) |
| **Unbound**      | DNS resolver for privacy & security             | [🔗 Unbound](https://github.com/NLnetLabs/unbound) |

