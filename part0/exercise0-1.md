```mermaid
sequenceDiagram
    participant Usuario
    participant Navegador
    participant Servidor
    participant BaseDeDatos

    Usuario->>Navegador: Escribir nota en el campo de texto
    Usuario->>Navegador: Hacer clic en el botón Save
    Note right of Usuario: La nota contiene el texto escrito
    
    Navegador->>Servidor: POST /new_note (nota en el cuerpo de la solicitud)
    Servidor->>BaseDeDatos: Guardar nueva nota en la base de datos
    BaseDeDatos-->>Servidor: Confirmación de guardado

    Servidor-->>Navegador: Respuesta con la nueva lista de notas
    Navegador-->>Usuario: Actualizar la página con la nueva lista de notas
