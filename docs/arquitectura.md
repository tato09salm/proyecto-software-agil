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