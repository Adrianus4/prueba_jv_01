# 📖 Documentación de la API (servicio-tarjetas)
Generada a partir del contrato **OpenAPI 3.1** aprobado por tarjetas.

## Endpoints Principales

### 1. Registrar Pedido
* **Método:** `POST`
* **Ruta:** `/api/v1/orders`
* **Código de Éxito:** `201 Created`
* **Ejemplo Request:**
```json
{
  "customerId": "CUST-8831",
  "customerEmail": "cliente@empresa.com",
  "notes": "Entregar en horario de oficina",
  "items": [
    {
      "sku": "SKU-PRO-01",
      "description": "Teclado Mecánico RGB",
      "quantity": 1,
      "unitPrice": 85.00
    }
  ]
}
```

### 2. Listar Pedidos
* **Método:** `GET`
* **Ruta:** `/api/v1/orders?status=PENDING&page=0&size=20`
* **Código de Éxito:** `200 OK`

### 3. Consultar Pedido por ID
* **Método:** `GET`
* **Ruta:** `/api/v1/orders/{orderId}`
* **Códigos:** `200 OK`, `404 Not Found`

### 4. Cancelar Pedido
* **Método:** `PUT`
* **Ruta:** `/api/v1/orders/{orderId}/cancel`
* **Regla de Negocio:** No se puede cancelar si el estado es `DISPATCHED` (HTTP 409 Conflict).
