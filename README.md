# SERVICIO-TARJETAS ⚡
> Microservicio autónomo desarrollado con **Quarkus 3.15 LTS** y **Java 21**.
> Equipo responsable: **tarjetas** | Grupo: `com.empresa.serviciotarjetas`

---

## 📋 Resumen del Servicio
"Microservicio para emitir y administrar tarjetas de crédito de clientes. Permite registrar tarjetas con límite de crédito y saldo disponible, registrar compras o cargos con validación de saldo, y bloquear tarjetas inmediatamente por sospecha de fraude o robo."

* **Enfoque de diseño:** Contract-First (OpenAPI 3.1 congelado).
* **Base de datos:** SQLite (Demo local portable) (Modo DEV: SQLite portátil / Modo PROD: SQL Server).
* **Seguridad:** JWT (SmallRye JWT).
* **Modo de Generación:** Medio.

---

## 🚀 Arranque Rápido en Modo Desarrollo
Para iniciar el microservicio con recarga en caliente (*Live Coding* de Quarkus):

```bash
./mvnw quarkus:dev
```

* **API Endpoints:** `http://localhost:8080/api/v1/orders`
* **Swagger UI / OpenAPI:** `http://localhost:8080/q/swagger-ui`
* **Quarkus Dev UI:** `http://localhost:8080/q/dev`

---

## 🧪 Ejecución de Pruebas Unitarias
Para correr la suite de pruebas automatizadas (@QuarkusTest + RestAssured):

```bash
./mvnw test
```

---

## 🩺 Observabilidad y Diagnóstico
El microservicio viene configurado de fábrica con los estándares corporativos:
* **Health Liveness:** `http://localhost:8080/q/health/live`
* **Health Readiness:** `http://localhost:8080/q/health/ready`
* **Métricas Prometheus:** `http://localhost:8080/q/metrics`
