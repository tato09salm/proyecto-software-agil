# Arquitectura del Sistema

## Diagrama de Arquitectura

```mermaid
graph LR
    A[Cliente Web<br>Next.js<br>Puerto 3000]
    B[API<br>FastAPI<br>Puerto 8000]
    C[(Base de Datos<br>PostgreSQL<br>Puerto 5432)]

    A -->|HTTP/JSON| B
    B -->|SQLAlchemy ORM| C

    style A fill:#61DAFB,stroke:#0f172a,stroke-width:2px,color:#0f172a
    style B fill:#009688,stroke:#0f172a,stroke-width:2px,color:#fff
    style C fill:#336791,stroke:#0f172a,stroke-width:2px,color:#fff

¿Por qué esta arquitectura se adapta mejor a metodologías Ágiles que a Cascada?
1. Separación por capas: El frontend, la API y la base de datos son independientes. Se
puede evolucionar una capa sin reescribir todo. Ejemplo: cambiar el diseño web sin
tocar la lógica de la API.
2. Entregas incrementales: Se construye y prueba una funcionalidad completa en cada
ciclo (ej: primero productos, luego usuarios, luego ventas), demostrando valor cada
vez.
3. Adaptación rápida: Si cambian los requisitos, se ajusta la API y la interfaz en el
siguiente Sprint sin afectar todo el sistema. En Cascada habría que reescribir la
planificación completa.
4. Pruebas continuas: Al tener componentes separados, se puede probar cada uno por
separado a medida que se construye, no esperar al final.
5. Menor riesgo: Si una funcionalidad se cancela o cambia, el resto del sistema sigue
funcionando. No se pierde todo el trabajo realizado.

En resumen: esta arquitectura permite cambiar fácilmente, entregar valor rápido y recibir
retroalimentación temprana — exactamente lo que promueve el enfoque Ágil