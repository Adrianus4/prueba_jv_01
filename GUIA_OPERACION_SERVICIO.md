# 🛠️ Guía de Operación y Monitoreo del Microservicio

## Probes para Kubernetes / Azure Container Apps
```yaml
livenessProbe:
  httpGet:
    path: /q/health/live
    port: 8080
  initialDelaySeconds: 5
  periodSeconds: 10

readinessProbe:
  httpGet:
    path: /q/health/ready
    port: 8080
  initialDelaySeconds: 3
  periodSeconds: 5
```

## Formato de Logs JSON
En producción (`%prod`), los logs se emiten en formato JSON estructurado listo para ingesta por FluentBit / Logstash / Azure Application Insights.
