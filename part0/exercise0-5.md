```mermaid
sequenceDiagram
    participant Usuario
    participant Navegador
    participant Servidor
    participant BaseDeDatos

    Usuario->>Navegador: Accede a https://studies.cs.helsinki.fi/exampleapp/spa
    Navegador->>Servidor: GET /spa
    Servidor-->>Navegador: HTML de la página SPA

    Navegador->>Servidor: GET /main.js
    Servidor-->>Navegador: main.js

    Navegador->>Servidor: GET /style.css
    Servidor-->>Navegador: style.css

    Note right of Navegador: El navegador procesa HTML, CSS y JS

    Navegador->>Servidor: GET /data.json (para obtener notas)
    Servidor->>BaseDeDatos: Solicitud de datos de notas
    BaseDeDatos-->>Servidor: Datos de notas (JSON)
    Servidor-->>Navegador: Datos de notas (JSON)

    Note right of Navegador: El navegador renderiza las notas en la página
