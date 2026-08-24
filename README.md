# Implementación y Despliegue de la Aplicación

# Integrantes

* **Mariana Valenzuela Penagos**
* **Maria Jose Rodriguez Oyola**


## 1. Conexión al servidor Linux

Para acceder a la máquina virtual mediante SSH se utiliza el siguiente comando --

```bash
ssh marmar@127.0.0.1 -p 2222
```

La conexión permite administrar el servidor Linux desde el equipo anfitrión y ejecutar las diferentes tareas relacionadas con Docker, los contenedores y la aplicación.

---

# 2. Arquitectura tecnológica

## Captura 1: Arquitectura tecnológica seleccionada

La solución está compuesta por tres elementos principales: frontend, backend y base de datos.

| Componente    | Tecnología         | Puerto | Función               |
| ------------- | ------------------ | -----: | --------------------- |
| Frontend      | React              |   8081 | Interfaz de usuario   |
| Backend       | Java + Spring Boot |   8080 | API REST              |
| Base de datos | PostgreSQL         |   5439 | Persistencia de datos |

### Descripción de la arquitectura

* **Frontend:** desarrollado con React, encargado de proporcionar la interfaz gráfica y permitir la interacción del usuario con la aplicación.
* **Backend:** desarrollado con Java y Spring Boot, encargado de procesar las solicitudes, ejecutar la lógica de negocio y exponer la API REST.
* **Base de datos:** PostgreSQL, utilizada para almacenar y consultar la información de la aplicación.
* **Docker:** permite ejecutar y aislar los diferentes componentes de la solución mediante contenedores.

---

# 3. Configuración del servidor Linux

## Captura 2: Información del servidor Linux

En esta evidencia se muestra la información del servidor Linux utilizado para ejecutar la aplicación.

<img width="1136" height="866" alt="Información del servidor Linux" src="https://github.com/user-attachments/assets/451aaec8-a3b8-4d3a-968e-0751139e389f" />

---

## Captura 3: Dirección IP de la máquina virtual

Se evidencia la dirección IP configurada en la máquina virtual, necesaria para establecer comunicación con el servidor y permitir el acceso a los servicios.

<img width="1147" height="598" alt="Dirección IP de la máquina virtual" src="https://github.com/user-attachments/assets/0cb56bab-3549-499d-add9-a98839d1c97f" />

<img width="1087" height="328" alt="Configuración de red" src="https://github.com/user-attachments/assets/2c425a73-5afb-4fcd-9848-4b0b7752468d" />

---

# 4. Implementación de Docker

## Captura 4: Docker funcionando correctamente

Se verifica que Docker se encuentra instalado y funcionando correctamente en el servidor Linux.

<img width="1133" height="676" alt="Docker funcionando" src="https://github.com/user-attachments/assets/b26720a0-e212-44c2-b330-8f47a3740d62" />

---

## Captura 4.1: Proyecto ejecutándose

Se evidencia la ejecución de los diferentes componentes del proyecto mediante Docker.

<img width="959" height="414" alt="Proyecto ejecutándose" src="https://github.com/user-attachments/assets/a0fa0cb7-3b74-4dbf-bebb-ac09c2ac1a7a" />

---

# 5. Ejecución y administración de contenedores

## Captura 5: Primer contenedor ejecutado

Se muestra la creación y ejecución del primer contenedor de la aplicación.

<img width="767" height="382" alt="Primer contenedor" src="https://github.com/user-attachments/assets/ee377a52-d4af-4698-9038-c32fd00fae4f" />

<img width="1594" height="948" alt="Contenedor ejecutándose" src="https://github.com/user-attachments/assets/a9cd7987-b6cf-473d-aed7-65e8493a9f3e" />

---

## Captura 6: Servicio web funcionando

Se verifica que el servicio web se encuentra disponible y funcionando correctamente.

<img width="1276" height="660" alt="Servicio web" src="https://github.com/user-attachments/assets/0294bb65-61df-44b7-9778-bd5ff3b97928" />

---

## Captura 7: Administración de los contenedores

Se muestran las diferentes operaciones de administración y supervisión de los contenedores Docker.

<img width="1849" height="917" alt="Administración de contenedores" src="https://github.com/user-attachments/assets/df1aad86-55af-4205-a941-92c09a8e646c" />

<img width="1090" height="917" alt="Contenedores Docker" src="https://github.com/user-attachments/assets/469cb7b7-4a77-480b-8aa7-dc9f66c664af" />

<img width="1732" height="985" alt="Administración Docker" src="https://github.com/user-attachments/assets/a2e7cd0d-d5d0-4748-b362-0663b052b2a6" />

---

# 6. Administración mediante Portainer

## Captura 8: Portainer funcionando

Se evidencia el acceso a Portainer, herramienta utilizada para administrar visualmente el entorno Docker.

<img width="1919" height="709" alt="Portainer funcionando" src="https://github.com/user-attachments/assets/338791a0-4173-47b6-b2ab-8dd3a2db1934" />

---

## Captura 9: Administración del entorno Docker desde Portainer

Desde Portainer se puede visualizar y administrar el entorno Docker, incluyendo los contenedores y recursos utilizados por la aplicación.

<img width="1902" height="938" alt="Administración mediante Portainer" src="https://github.com/user-attachments/assets/fde80679-d420-42c6-b32c-8611674db018" />

<img width="1828" height="914" alt="Entorno Docker en Portainer" src="https://github.com/user-attachments/assets/9686ede6-9261-44ba-9204-d8a8315fd07c" />

---

# 7. Gestión de volúmenes

## Captura 10: Volumen creado

Se crea un volumen Docker para permitir la persistencia de información.

### Creación del volumen

<img width="520" height="234" alt="Creación del volumen" src="https://github.com/user-attachments/assets/84add829-78ee-43bc-baa3-9114a2689182" />

<img width="1370" height="547" alt="Volumen creado" src="https://github.com/user-attachments/assets/d7177dd9-ea50-490a-bdd2-6db34a06f754" />

---

## Captura 11: Eliminación de pruebas

Se eliminan los contenedores y recursos utilizados durante las pruebas iniciales para dejar limpio el entorno de trabajo.

<img width="843" height="169" alt="Eliminación de pruebas" src="https://github.com/user-attachments/assets/d75da1d7-77eb-4d8b-80af-7938f184993a" />

---

# 8. Dockerización del frontend

## Captura 12: Dockerfile del frontend

Se presenta el archivo `Dockerfile` utilizado para construir la imagen Docker del frontend desarrollado con React.

<img width="1919" height="986" alt="Dockerfile frontend" src="https://github.com/user-attachments/assets/889a842f-25c2-49c4-9ad8-81fa8c06b3ca" />

<img width="1157" height="486" alt="Configuración Docker frontend" src="https://github.com/user-attachments/assets/8f845f55-6672-4ff8-bcd2-839403fd611a" />

---

## Captura 13: Imagen Docker del frontend construida

Se evidencia la construcción exitosa de la imagen Docker correspondiente al frontend.

<img width="1207" height="365" alt="Imagen frontend" src="https://github.com/user-attachments/assets/31d1613b-ed44-4327-93ca-cc98321172ad" />

<img width="1919" height="512" alt="Imagen Docker frontend" src="https://github.com/user-attachments/assets/bfd1dc94-7baf-4fbd-a3cd-9b0a67a08817" />

---

## Captura 14: Frontend funcionando dentro del contenedor

Se comprueba que la aplicación frontend puede ejecutarse correctamente desde su contenedor Docker.

<img width="1919" height="977" alt="Frontend funcionando" src="https://github.com/user-attachments/assets/82d1b69b-1b1f-4cac-9406-23ad9f5f2743" />

---

# 9. Dockerización del backend

## Captura 15: Dockerfile del backend

Se presenta el `Dockerfile` utilizado para construir la imagen Docker del backend desarrollado en Java con Spring Boot.

<img width="1168" height="887" alt="Dockerfile backend" src="https://github.com/user-attachments/assets/aab16270-b4fb-4dd3-b45b-75418939ffa5" />

### Construcción de la imagen

<img width="1919" height="255" alt="Construcción de imagen backend" src="https://github.com/user-attachments/assets/c0bea1ad-608d-4cd1-b883-7277f7f85b36" />

---

## Captura 16: Imagen Docker del backend

Se evidencia la imagen Docker generada para el backend.

<img width="1111" height="226" alt="Imagen backend" src="https://github.com/user-attachments/assets/e0ca179e-078e-4d6f-94df-f72273aa5b36" />

---

## Captura 17: Backend funcionando

Se verifica que el backend se encuentra ejecutándose correctamente dentro del entorno Docker.

<img width="1919" height="572" alt="Backend funcionando" src="https://github.com/user-attachments/assets/2f2d840a-c1cc-4ac8-a5a2-df61935657a7" />

---

# 10. Implementación de la base de datos

## Captura 18: Contenedor de base de datos funcionando

Se evidencia la ejecución del contenedor correspondiente a PostgreSQL.

<img width="1919" height="991" alt="PostgreSQL funcionando" src="https://github.com/user-attachments/assets/3d5dc243-a228-43d4-8cac-1e7b9b1adc13" />

---

## Captura 19: Base de datos creada

Se evidencia la creación de la base de datos PostgreSQL que será utilizada por el backend para almacenar la información de la aplicación.

<img width="1890" height="440" alt="Base de datos creada" src="https://github.com/user-attachments/assets/32faf8d9-f928-4ccc-af87-afa114091600" />

---

## Captura 20: Volumen asociado a la base de datos

Se evidencia el volumen utilizado por PostgreSQL para mantener la persistencia de los datos.

<img width="1919" height="272" alt="Volumen PostgreSQL" src="https://github.com/user-attachments/assets/0a65815a-2fe0-41a8-b705-a18c7f6a3d96" />

<img width="1919" height="363" alt="Volumen asociado a PostgreSQL" src="https://github.com/user-attachments/assets/1983d30f-30d6-46d5-8aa8-4e99ef2e83c3" />

---

# 11. Configuración de conexión

## Captura 21: Configuración de conexión

Se presenta la configuración utilizada para establecer la comunicación entre los diferentes componentes de la aplicación.

<img width="1142" height="763" alt="Configuración de conexión" src="https://github.com/user-attachments/assets/ca79f185-3036-4070-88b5-744dd846c3c8" />

### Levantamiento del Compose principal

Se levanta el archivo Docker Compose principal encargado de ejecutar los servicios del frontend y backend.

<img width="1029" height="720" alt="Docker Compose frontend y backend" src="https://github.com/user-attachments/assets/0bf8b743-a5a7-4fd2-b92e-90b10589d9f3" />

---

# 12. Operaciones de la aplicación

## Captura 22: Operación de lectura

Se realiza una operación de lectura para comprobar que la aplicación puede consultar correctamente la información almacenada.

<img width="1870" height="353" alt="Operación de lectura" src="https://github.com/user-attachments/assets/911b6af5-d32b-4db0-85b6-3e41d5054d7c" />

---

## Captura 23: Operación de escritura

Se realiza una operación de escritura para comprobar que la aplicación puede registrar información correctamente en la base de datos.

<img width="1499" height="293" alt="Operación de escritura" src="https://github.com/user-attachments/assets/84de75a7-37b1-4aa7-aec8-744e3f3a8960" />

<img width="1910" height="904" alt="Resultado de escritura" src="https://github.com/user-attachments/assets/eeee3159-8efa-4de7-a7c3-108df03ec373" />

---

# 13. Comunicación entre servicios

## Captura 24: Logs mostrando comunicación exitosa

Los logs permiten comprobar que existe comunicación correcta entre los diferentes componentes de la aplicación.

<img width="1660" height="912" alt="Logs de comunicación" src="https://github.com/user-attachments/assets/7c24bb4e-d780-4666-83c9-ec0668433c44" />

---

# 14. Prueba funcional de la aplicación

## Captura 25: Frontend funcionando

Se accede a la interfaz de la aplicación y se realiza el registro de un nuevo usuario.

<img width="1434" height="933" alt="Registro de usuario" src="https://github.com/user-attachments/assets/41021b6c-aeb3-4ef2-9f5c-6d3b51a832fb" />

---

## Captura 26: Solicitud del frontend hacia el backend

Se evidencia la solicitud enviada desde el frontend hacia la API REST del backend.

---

## Captura 27: Respuesta recibida desde el backend

Se evidencia la respuesta generada por el backend después de procesar correctamente la solicitud enviada desde el frontend.

---

## Captura 28: Aplicación completa funcionando

Se comprueba el funcionamiento integrado de los diferentes componentes:

```text
Frontend → Backend → Base de datos
```

La prueba demuestra que los servicios pueden comunicarse correctamente y que la aplicación funciona como una solución integrada.

---

# 15. Docker Compose

## Captura 29: Archivo Docker Compose

El archivo `docker-compose.yml` permite definir y ejecutar los diferentes servicios que conforman la solución.

La configuración contempla los elementos necesarios para levantar el entorno completo:

* Frontend.
* Backend.
* Base de datos.
* Redes.
* Volúmenes.
* Configuración de los servicios.

<img width="1380" height="697" alt="Docker Compose" src="https://github.com/user-attachments/assets/4c387909-e297-4c56-916c-9f63937233e5" />

<img width="1426" height="742" alt="Docker Compose configuración" src="https://github.com/user-attachments/assets/f92eb389-d6c5-42da-bae8-25b10072339d" />

<img width="1315" height="652" alt="Docker Compose servicios" src="https://github.com/user-attachments/assets/b9134251-9a6a-4f02-80ae-1af01f252ad5" />

<img width="1197" height="645" alt="Docker Compose configuración final" src="https://github.com/user-attachments/assets/fd114ce1-8aee-4071-9970-320bab78e9f6" />

---

# 16. Administración del ciclo de vida de los servicios

## Captura 30: Todos los servicios funcionando

Se verifica que todos los servicios definidos en Docker Compose se encuentran activos y funcionando correctamente.
<img width="1917" height="356" alt="image" src="https://github.com/user-attachments/assets/bbe9d571-a8d8-41e3-a3c3-8e7fe92eb42b" />


---

## Captura 31: Servicios detenidos

Se detienen los servicios para comprobar el correcto funcionamiento de las operaciones de administración del entorno Docker.
<img width="1917" height="370" alt="image" src="https://github.com/user-attachments/assets/08924c39-fc1a-478c-a23a-c8dafcb418ec" />


---

## Captura 32: Servicios recuperados

Se vuelven a iniciar los servicios y se comprueba que la aplicación puede recuperarse correctamente después de haber sido detenida.
<img width="1917" height="467" alt="image" src="https://github.com/user-attachments/assets/78681c2f-894b-4e74-aa4b-5fc4387ad833" />


---

## Captura 33: Servicios reconstruidos

Se reconstruyen los servicios mediante Docker para comprobar que las imágenes pueden generarse nuevamente y que la aplicación continúa funcionando correctamente.
<img width="1865" height="990" alt="image" src="https://github.com/user-attachments/assets/2fa098b7-d2dc-4ab7-a00f-76ceae746f87" />

---

# 17. Acceso desde diferentes equipos

## Captura 34: Aplicación funcionando desde el equipo anfitrión

Se verifica el acceso a la aplicación desde el equipo anfitrión donde se encuentra ejecutándose la máquina virtual.
<img width="1817" height="1011" alt="image" src="https://github.com/user-attachments/assets/80a3a31e-d51a-48d1-a28b-5cae780e8317" />



---

## Captura 35: Aplicación funcionando desde otro equipo de la intranet

Finalmente, se comprueba el acceso a la aplicación desde otro equipo conectado a la misma red interna.

Esta prueba permite verificar que los servicios publicados por el servidor pueden ser consumidos desde otro dispositivo de la intranet.
<img width="474" height="1600" alt="image" src="https://github.com/user-attachments/assets/3250111c-f461-4e47-a450-de3a31f2b4e6" />

---

# 18. Flujo general de funcionamiento

La arquitectura implementada sigue el siguiente flujo:

```text
                    ┌─────────────────┐
                    │     Usuario     │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │    Frontend     │
                    │      React      │
                    │     :8081      │
                    └────────┬────────┘
                             │
                         HTTP/REST
                             │
                             ▼
                    ┌─────────────────┐
                    │     Backend     │
                    │ Java + Spring   │
                    │      :8080      │
                    └────────┬────────┘
                             │
                         SQL/JDBC
                             │
                             ▼
                    ┌─────────────────┐
                    │   PostgreSQL    │
                    │      :5439      │
                    └─────────────────┘
```

Todos los componentes son ejecutados mediante Docker y se encuentran conectados dentro del entorno definido mediante Docker Compose.

---

# 19. Resumen de la implementación

La implementación permitió:

1. Configurar y acceder al servidor Linux mediante SSH.
2. Verificar la configuración de red de la máquina virtual.
3. Instalar y comprobar el funcionamiento de Docker.
4. Crear y administrar contenedores.
5. Administrar el entorno mediante Portainer.
6. Crear volúmenes para garantizar la persistencia.
7. Dockerizar el frontend desarrollado en React.
8. Dockerizar el backend desarrollado en Java y Spring Boot.
9. Ejecutar PostgreSQL dentro de un contenedor.
10. Asociar un volumen a la base de datos.
11. Configurar la comunicación entre frontend, backend y base de datos.
12. Comprobar operaciones de lectura y escritura.
13. Verificar la comunicación mediante logs.
14. Ejecutar pruebas funcionales desde el frontend.
15. Implementar el entorno completo mediante Docker Compose.
16. Detener, recuperar y reconstruir los servicios.
17. Comprobar el acceso desde el equipo anfitrión.
18. Comprobar el acceso desde otro equipo de la intranet.

---

# 20. Resultado final

Como resultado, se obtuvo una aplicación completamente contenerizada y funcional, compuesta por:

```text
React
  │
  │ Puerto 8081
  ▼
Spring Boot
  │
  │ Puerto 8080
  ▼
PostgreSQL
  │
  │ Puerto 5439
  ▼
Volumen persistente
```

La solución permite ejecutar, administrar, detener, recuperar y reconstruir los diferentes servicios utilizando Docker y Docker Compose, manteniendo además la persistencia de la información almacenada en PostgreSQL.

