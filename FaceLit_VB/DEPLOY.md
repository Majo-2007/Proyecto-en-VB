# FaceLit — Despliegue multicapa con Docker

## 1. Arquitectura tecnológica seleccionada

| Componente    | Tecnología                              | Puerto (host) | Función                                   |
| ------------- | ---------------------------------------- | -------------: | ------------------------------------------ |
| Frontend      | Expo (React Native) → build web + Nginx  |           8081 | Interfaz de usuario (control de asistencia con reconocimiento facial) |
| Backend       | Java 17 + Spring Boot 3.4.1              |           8080 | API REST (auth JWT, negocio, correo)      |
| Base de datos | PostgreSQL 16                            |           5439 | Persistencia                              |
| Migraciones   | Liquibase 5.0.2 (perfil `tooling`)       |               — | Versionado del esquema de BD              |

Comunicación:

```
Navegador ──HTTP──▶ Frontend (Nginx, :8081)
Navegador ──HTTP/REST──▶ Backend (Spring Boot, :8080)
Backend ──JDBC (red Docker "facelit-net")──▶ PostgreSQL (:5432 interno)
```

## 2. Estructura Docker del proyecto

```
FaceLit_VB/
├── docker-compose.yml        ← orquesta los 4 servicios
├── .env.example               ← variables de entorno (copiar a .env)
├── FaceLit/                   ← frontend
│   ├── Dockerfile             (multi-stage: build Expo web + Nginx)
│   └── nginx.conf
├── FaceLit-Backend/           ← backend
│   └── Dockerfile             (multi-stage: build Maven + JRE)
└── FaceLit-DB/                ← base de datos y migraciones
    ├── docker-compose.yml     (compose original, standalone)
    └── docker/liquibase/Dockerfile
```

## 3. Puesta en marcha

```bash
# 1. Ubicarse en la raíz del proyecto
cd FaceLit_VB

# 2. Crear el archivo de variables de entorno
cp .env.example .env
# Editar .env y ajustar FRONTEND_API_URL con la IP de la VM
# (necesaria para que el navegador del cliente alcance el backend)

# 3. Levantar los 3 servicios principales
docker compose up -d --build

# 4. Verificar
docker compose ps

# 5. (Opcional) Aplicar las migraciones de base de datos
docker compose --profile tooling run --rm liquibase update
```

Acceso:

- Frontend: `http://IP_DE_LA_VM:8081`
- Backend (API): `http://IP_DE_LA_VM:8080`
- Postgres: `IP_DE_LA_VM:5439`

## 4. Notas importantes

- **`FRONTEND_API_URL`**: el frontend se compila como archivos estáticos que
  corren en el navegador del cliente, fuera de la red interna de Docker. Por
  eso `EXPO_PUBLIC_API_URL` debe apuntar a una IP alcanzable desde el
  navegador (la IP de la VM), **no** al nombre del servicio `backend`.
- **`DB_URL` del backend**: dentro de la red Docker, el backend sí usa el
  nombre del servicio `postgres:5432` (resuelto por la red `facelit-net`).
- El volumen `postgres_data` conserva los datos aunque se reinicien o
  reconstruyan los contenedores (`docker compose down && docker compose up -d --build`).
- El `docker-compose.yml` de `FaceLit-DB/` se conserva para poder levantar
  solo la base de datos de forma aislada si se necesita, pero para la
  entrega de la actividad se usa el compose raíz, que integra los 3
  componentes.

## 5. Pruebas de recuperación sugeridas (Actividad 15)

```bash
docker compose stop
docker compose ps
docker compose start

docker compose down
docker compose up -d

docker compose up -d --build
```
