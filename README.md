# devops-ci-cd-lab
Diseñar e implementar un pipeline de Integración Continua y Entrega Continua (CI/CD) utilizando GitHub Actions para automatizar la construcción, validación, empaquetado y despliegue de una aplicación Node.js sobre Azure Container Apps, empleando Docker como tecnología de contenedores, Azure Container Registry como repositorio de imágenes y autenticación segura mediante Microsoft Entra ID con OpenID Connect (OIDC).

Arquitectura 

                  
git push (main)
      │
      ▼
GitHub Actions (ubuntu-latest)
      │
      ├─ 1. Checkout código
      ├─ 2. Auth → Microsoft Entra ID (OIDC)
      ├─ 3. Login Docker → Azure Container Registry
      ├─ 4. docker build & push (tag SHA)
      └─ 5. Deploy → Azure Container Apps
                                     │
                                     ▼
                           Servicio en vivo (HTTPS)
                           
Stack tecnológico

| Componente           | Tecnología                                 |
| -------------------- | ------------------------------------------ |
| Aplicación           | Node.js + Express                          |
| Contenedor           | Docker                                     |
| Registro de imágenes | Azure Container Registry (ACR)             |
| Plataforma           | Azure Container Apps                       |
| CI/CD                | GitHub Actions                             |
| Autenticación        | Microsoft Entra ID + OpenID Connect (OIDC) |
