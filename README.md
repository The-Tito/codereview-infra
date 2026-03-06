# 🛠️ codereview-infra

Repositorio de infraestructura para el frontend de **CodeReview** — una plataforma para realizar revisiones de código de forma colaborativa.

Este repositorio contiene la configuración de Docker necesaria para levantar el frontend del proyecto en un entorno local o de producción.

> 🌐 **Deploy en producción:** [https://codereview-front.vercel.app](https://codereview-front.vercel.app)

---

## 📦 Requisitos previos

Asegúrate de tener instalado lo siguiente antes de continuar:

- [Docker](https://www.docker.com/get-started) (v20+)
- [Docker Compose](https://docs.docker.com/compose/) (v2+)
- El repositorio del frontend [`codereview-front`](https://github.com/The-Tito/codereview-front) clonado **al mismo nivel** que este repositorio

### Estructura de carpetas esperada

```
├── codereview-front/   ← repositorio del frontend
└── codereview-infra/   ← este repositorio
```

---

## 🚀 Cómo levantar el proyecto

### 1. Clona ambos repositorios

```bash
git clone https://github.com/The-Tito/codereview-infra.git
git clone https://github.com/The-Tito/codereview-front.git
```

### 2. Ingresa al repositorio de infraestructura

```bash
cd codereview-infra
```

### 3. Configura las variables de entorno

Copia el archivo `.env.example` (si existe) o crea un archivo `.env` en la raíz con las variables necesarias:

```bash
cp .env.example .env
```

Edita el archivo `.env` con los valores correspondientes a tu entorno.

### 4. Levanta los servicios con Docker Compose

```bash
docker compose up --build
```

Esto construirá la imagen del frontend y levantará el contenedor. El servicio quedará disponible en:

```
http://localhost:3000
```

### 5. (Opcional) Ejecutar en segundo plano

```bash
docker compose up --build -d
```

---

## 🔧 Servicios incluidos

| Servicio | Descripción            | Puerto |
| -------- | ---------------------- | ------ |
| `web`    | Frontend de CodeReview | `3000` |

---

## 🛑 Detener los servicios

```bash
docker compose down
```

---

## 📁 Estructura del repositorio

```
codereview-infra/
├── docker-compose.yml   # Configuración principal de Docker Compose
├── init/                # Scripts de inicialización (si aplica)
├── .env                 # Variables de entorno (no se versiona)
└── README.md
```

---
