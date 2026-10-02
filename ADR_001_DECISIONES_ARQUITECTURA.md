# 🏛️ ADR-001: Decisiones de Arquitectura para servicio-tarjetas

## Estado
**Aprobado por el Agente Arquitecto y Validado por el Usuario**

## Contexto
Se requiere construir un microservicio para la gestión de pedidos con alto rendimiento, arranque instantáneo y mínimo consumo de recursos en entornos de contenedores (Kubernetes/Azure).

## Decisiones Adoptadas
1. **Framework Quarkus 3.x sobre Java 21:**
   - Razón: Tiempos de arranque en milisegundos, menor huella de memoria RSS y soporte nativo GraalVM.
2. **Contract-First con OpenAPI 3.1:**
   - Razón: Congelar el contrato antes del desarrollo garantiza desacoplamiento entre frontend/backend y cero discrepancias de especificación.
3. **Hibernate ORM con Panache:**
   - Razón: Elimina código repetitivo de DAOs manteniendo la potencia de JPA.
4. **Perfiles Duales de Base de Datos (%dev SQLite portátil / %prod SQL Server):**
   - Razón: Portabilidad total para demos locales en cualquier máquina sin requerir un servidor SQL Server encendido, manteniendo total compatibilidad con el entorno corporativo de producción.
