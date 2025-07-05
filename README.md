# Portfolio
Synthèse générale du projet de gestion de ressources humaines

# 🧠 DevOps Portfolio – Artur Tchinde Lambo

Welcome to my DevOps and Backend Engineering portfolio.

This repository serves as a central showcase of my professional projects, built using microservices architecture, containerized environments, secure APIs, and CI/CD best practices.

---

## 🔹 Projects Overview

| Project | Description | Stack | Link |
|--------|-------------|-------|------|
| 🧩 **Team Microservice** | Manages team entities (CRUD, authentication, data model) | .NET 8, EF Core, Docker, JWT | [View Repo](https://github.com/LAMBOFIRSTECH/Team-microservice) |
| 🔧 **Infra Microservice** | Handles system/infrastructure-level logic and automation | .NET, Docker, API REST | [View Repo](https://github.com/LAMBOFIRSTECH/Infra-microservice) |
| 📚 **Competencies Microservice** | Skill and competencies manager with secure endpoints | .NET, Entity Framework, Docker | [View Repo](https://github.com/LAMBOFIRSTECH/Competencies-microservice) |
| 🎓 **Major Microservice** | Manages academic majors & learning paths | .NET 8, SQL Server, REST | [View Repo](https://github.com/LAMBOFIRSTECH/Major-microservice) |
| 🌐 **Web Application** | Frontend + API bridge for microservices | ASP.NET MVC, Bootstrap, REST | [View Repo](https://github.com/LAMBOFIRSTECH/WebApplication) |
| 📦 **NuGet Package** | Custom .NET class library for shared logic | C#, NuGet | [View Repo](https://github.com/LAMBOFIRSTECH/Nuget-Package) |

---

## 🛠️ Technologies & Tools

- **Languages**: C#, Bash, YAML, Python
- **Frameworks**: .NET 8 / .NET Core, Entity Framework Core
- **DevOps Tools**: Docker, Docker Compose, GitLab CI, Trivy for non vulnerabilities docker images and Docker bench to secure docker container
- **Secrets & Security**: HashiCorp Vault(Secrets) Consul(For services discovery) - Nomad (For orchestration), AppRole (each API need credentials to interact with Vault using AppRole), JWT (Asymetric algorithm)
- **Automation**: Ansible, Bash and python scripts, Git hooks
- **Observability**: Prometheus, Grafana, ELK, Graylog
- **Auth & API Gateway**: Keycloak (IAM, Standard Ldap and SSO), Nginx, Traefik, Gravitee
- **Databases**: SQL Server (On a windows server Machine 2019), PostgreSQL, MongoDB
- **Infrastructure**: Nomad, Consul, OpenLDAP, Redis

---

## ⚙️ Key Highlights

- Clean Architecture + Domain-Driven Design principles
- Fully containerized microservices, API-first approach
- Dockerfile + docker-compose support for each project
- All our docker images are dowloading on DockerHub
- CI/CD-ready projects (with pipelines in GitLab CI or GitHub Actions)
- Secure API design (JWT, OAuth2, Vault-based secret injection)
- Scalable and modular backend systems

---

## 📌 About Me

I'm an Engineer specialized in DevOps and scalable backend systems.  
I've worked on real-world infrastructures at **ATOS** and **Meloaude**, where I led projects from development to containerized deployment with strong security and monitoring layers.

I believe in reliable delivery, transparency, and long-term system stability.  
📍 Currently open to full-time DevOps positions (Strasbourg or remote).  
📩 [Contact me via email](mailto:artur.tchindelambo@hotmail.com)

---

## 👀 Bonus Ideas (optional)

- Add a diagram: `architecture.png` or draw.io link
- Add demo screenshots or .gif previews
- Use GitHub badges for language stats and build

---

Thanks for visiting this repo 🙏  
Feel free to explore, fork, or reach out!
