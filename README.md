# 🚀 n8n Crypto Monitor 

Este repositorio contiene el flujo de trabajo (workflow) desarrollado para el mini-proyecto final de automatización. El sistema monitoriza el precio de Bitcoin y genera alertas inteligentes basadas en la volatilidad del mercado.

## 🛠️ Arquitectura del Flujo

### 1. Entrada (Ingesta)
* **Periodicidad**: Ejecución diaria a las 09:00 AM mediante `Schedule Trigger`.
* **Fuente de datos**: API pública de CoinGecko (HTTP Request).

### 2. Procesado (Lógica de Negocio)
* **Validación**: Filtro `If` que solo permite el flujo de datos si la variación en 24h es ≥ 5%.
* **Transformación**: Nodo `Edit Fields` para normalizar el esquema de datos (Fecha, Precio, Cambio).

### 3. Salida (Notificación)
* **Canal**: Discord (Webhook).
* **Contenido**: Alerta enriquecida con datos dinámicos del activo procesado.

### 4. Operación y Observabilidad
* **Gestión de Errores**: Integración con un Workflow de errores centralizado (Ej.4).
* **Logs**: Persistencia de ejecuciones activada para auditoría técnica.

## 📦 Instalación
1. Descarga el archivo `workflow.json` de este repositorio.
2. Impórtalo en tu instancia de n8n.
3. Configura tu Webhook de Discord en el nodo de salida.
