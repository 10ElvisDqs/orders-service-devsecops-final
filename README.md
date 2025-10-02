
# 🛒 Orders Service - DevSecOps Final Project

[![CI/CD Pipeline](https://img.shields.io/badge/CI%2FCD-Jenkins-blue)](https://www.jenkins.io/) 
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

Proyecto final del diplomado de **DevSecOps**, que implementa un **microservicio de órdenes** junto con una **pipeline CI/CD completa**, integrando análisis de seguridad, despliegue con Docker y gestión de artefactos.

---
<p align="center">
  <img width="2669" height="585" alt="image" src="https://github.com/user-attachments/assets/7b9de3d0-defc-4731-9e4d-b842f6dbf9a3" />
</p>

<p align="center">
  <img width="984" height="350" alt="image" src="https://github.com/user-attachments/assets/a64bbd11-befc-4ae6-aaf9-b55dd242a75a" />
</p>

<p align="center">
  <img width="603" height="399" alt="image" src="https://github.com/user-attachments/assets/7f18e091-50c9-4190-a44a-20db933ecab8" />
</p>


---

## 📖 Descripción

Este repositorio contiene el proyecto final del módulo de DevSecOps del diplomado.  
Incluye un **microservicio de órdenes** en Node.js y una **pipeline automatizada** en Jenkins que cubre todas las fases de seguridad y despliegue.

---

## 🚀 Funcionalidades de la Pipeline DevSecOps

1. **Checkout de código**  
   Obtiene la última versión del código desde GitHub.

2. **SAST - Análisis estático de código**  
   - Herramienta: **Semgrep**  
   - Genera reportes JSON con hallazgos de seguridad.

3. **SCA - Análisis de dependencias**  
   - Herramienta: **OWASP Dependency-Check**  
   - Detecta vulnerabilidades en librerías y dependencias.

4. **PaC - Policy as Code**  
   - Herramienta: **Checkov**  
   - Escanea Dockerfile y valida políticas de infraestructura.

5. **Docker Build & Trivy Scan**  
   - Construye la imagen Docker del microservicio.  
   - Escanea la imagen con **Trivy** para vulnerabilidades HIGH y CRITICAL.

6. **DAST - Escaneo dinámico de la aplicación**  
   - Herramienta: **OWASP ZAP**  
   - Realiza un escaneo baseline de la aplicación desplegada.

7. **Integración con DefectDojo**  
   - Todos los reportes (Semgrep, Dependency-Check, Checkov, Trivy, ZAP) se suben automáticamente a DefectDojo para centralizar hallazgos.

8. **Deploy en Staging**  
   - Despliegue del microservicio usando **Docker Compose**.

9. **Gestión de Artefactos**  
   - Reportes y logs subidos automáticamente a **Google Drive** usando rclone.

---

## 🧰 Tecnologías y Herramientas

- Node.js (Orders Service)  
- Docker & Docker Compose  
- Jenkins (CI/CD)  
- Semgrep (SAST)  
- OWASP Dependency-Check (SCA)  
- Checkov (PaC)  
- Trivy (Docker Image Scanning)  
- OWASP ZAP (DAST)  
- DefectDojo (Gestión de hallazgos)  
- Google Drive / rclone (Almacenamiento de artefactos)

---

## ⚙️ Cómo usarlo

1. Clonar el repositorio:  
```bash
git clone https://github.com/TU_USUARIO/orders-service-devsecops-final.git
cd orders-service-devsecops-final
```

2. Configurar Jenkins con credenciales:

   * Token de DefectDojo
   * SMTP para notificaciones por correo
   * Rclone configurado para Google Drive

3. Ejecutar la pipeline CI/CD:

   * Automatizada en Jenkins
   * O ejecutar manualmente cada etapa según necesidad



## 📂 Estructura del repositorio

```
.
├── Dockerfile
├── docker-compose.yml
├── Jenkinsfile
├── src/                # Código fuente del microservicio
├── dependency-check-reports/
├── trivy-reports/
├── zap-reports/
├── checkov-report.json
├── semgrep-results.json
└── README.md
```

---

## 📝 Reportes y Artefactos

Todos los reportes generados por la pipeline se almacenan y pueden consultarse en:

* **DefectDojo**: Para hallazgos de seguridad
* **Google Drive**: Para artefactos y logs completos de cada build

---

## 📬 Notificaciones

* La pipeline envía notificaciones vía **correo electrónico** en caso de fallos o alertas críticas.

---

## ⚖️ Licencia

Este proyecto está bajo la **Licencia MIT**.
