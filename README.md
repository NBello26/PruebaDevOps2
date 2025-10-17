## ¿Qué hace el workflow?

### CI/CD Pipeline con GitHub Actions

Este proyecto utiliza un workflow de CI/CD automatizado mediante **GitHub Actions** para pruebas, análisis y despliegue de una aplicación Node.js.

### Disparadores

El workflow se ejecuta en los siguientes casos:
- Push a `main` o `workflow`
- Pull Request hacia `main` o `workflow`

---

### Job 1: `build-and-test`

Se encarga de validar la calidad del código.

**Pasos:**
1. Descarga el repositorio
2. Configura Node.js (v18)
3. Instala dependencias (`npm install`)
4. Corre pruebas unitarias con Karma + Jasmine
5. Ejecuta ESLint para corregir estilo
6. Realiza escaneo de seguridad con Snyk (no bloqueante)
7. Lanza análisis de código con SonarCloud

---

### Job 2: `docker`

Solo se ejecuta si el anterior fue exitoso.

**Pasos:**
1. Inicia sesión en Docker Hub
2. Construye y etiqueta imagen Docker
3. Publica imagen (`latest` y por commit) en Docker Hub

---

### Secretos requeridos

Configura estos secretos en GitHub(Deben ser solicitados al creador del proyecto NBello26):
- `SNYK_TOKEN`
- `SONAR_TOKEN`
- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

---

Este pipeline garantiza que todo código subido esté probado, analizado y desplegado de forma segura.


## Como escribir el codigo

| Elemento              | Convención   | Ejemplo                        |
| --------------------- | ------------ | ------------------------------ |
| Variables | `camelCase`  | `className`, `descripcionId` |
| Componentes y funciones        | `PascalCase` | `Boton`, `ListaCard` , `etc`          |
| Carpetas   | `kebab-case` | `lista-card/`      |
