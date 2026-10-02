# 🧪 Guía de Pruebas y Cobertura

## Estrategia de Pruebas
* **Pruebas de Componente con @QuarkusTest:** Levanta el contexto ligero de Quarkus en menos de 1 segundo.
* **Aislamiento con @InjectMock:** Para servicios externos o mensajería Kafka.
* **RestAssured:** Pruebas fluidas sobre endpoints HTTP simulando llamadas reales.

## Ejecución con Cobertura (JaCoCo)
```bash
./mvnw verify
```
El reporte HTML de cobertura se genera en `target/jacoco-report/index.html`.
