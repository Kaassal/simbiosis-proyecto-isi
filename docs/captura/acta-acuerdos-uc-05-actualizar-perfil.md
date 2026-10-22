# Acta de acuerdos de UC-05 · Actualizar perfil

| Campo | Valor |
| --- | --- |
| Proyecto | Proyecto Simbiosis |
| Caso de uso | UC-05 · Actualizar perfil |
| Estado | Vigente |
| Versión | 1.1 |
| Fecha de redacción | 10/10/2026 |
| Aprobación docente para L06 | 10/10/2026 |
| Tipo | Acta simulada de aclaración |
| Finalidad | Concretar el comportamiento que se describirá en L06. |

Esta acta recoge las respuestas que el analista habría obtenido al consultar a una persona usuaria. No documenta una entrevista real. El profesor ha aprobado las aclaraciones para L06. Complementan el catálogo canónico para el alcance seleccionado; no modifican su redacción.

## 1. Participantes y alcance

En la simulación participan un analista y una persona usuaria registrada. La persona quiere actualizar su propio perfil y conservar los cambios.

La consulta se centra en datos personales, datos de contacto y preferencias dietéticas. La persona ya tiene una cuenta activa y una sesión iniciada. El registro, el inicio de sesión, el cambio de contraseña y la eliminación de la cuenta quedan fuera de esta consulta.

## 2. Acuerdos

### Datos que se pueden modificar

- La persona puede consultar los valores guardados antes de modificarlos.
- Para esta descripción se consideran el nombre completo, el teléfono, la dirección postal y las preferencias dietéticas.
- El alias y el correo electrónico se muestran como datos de consulta. No se pueden modificar, conforme a FR-019.
- El nombre completo y el teléfono siguen siendo obligatorios. La dirección postal es opcional.
- Las preferencias son opcionales. La persona puede seleccionar ninguna, una o varias: vegana, sin gluten y baja en carbohidratos.
- Las preferencias no son datos de salud ni sustituyen el registro de alergias. Esta consulta no modifica datos de salud.

### Validación de los cambios

- El nombre completo y el teléfono no pueden quedar vacíos. Un valor formado solo por espacios se considera vacío.
- El teléfono conserva las reglas de formato del registro, incluidos los prefijos internacionales.
- Si un dato no es válido, el sistema identifica el campo y explica qué debe corregirse. Conserva los valores introducidos y no guarda ningún cambio.
- La persona puede corregir los datos y volver a solicitar el guardado.

### Guardado y cancelación

- La edición no cambia por sí sola los datos guardados. La persona debe solicitar el guardado.
- Cuando los datos son válidos, el sistema guarda conjuntamente los cambios y confirma que el perfil se ha actualizado.
- Si la persona cancela antes de guardar, se descartan los cambios de esa edición. El perfil conserva los valores anteriores.
- Si el sistema no puede guardar, informa del problema y no confirma la actualización. Conserva los valores introducidos para que la persona pueda reintentar el guardado. Los datos guardados permanecen sin cambios.

## 3. Fuentes y relación con los requisitos

| Fuente | Respaldo |
| --- | --- |
| [Catálogo canónico de requisitos](../requisitos/catalogo-requisitos.md), UR-03 y FR-019 | Actualización de información personal y preferencias; exclusión del alias y del correo electrónico. |
| [Acta general de captura](acta-captura-requisitos-generales.md), apartado 1.1 | Datos obligatorios y opcionales de la cuenta. |
| [Acta de UR-01](acta-captura-requisitos-ur-01.md), apartado 2.1 | Teléfono obligatorio y admisión de prefijos internacionales. |

La selección de campos para esta descripción, las opciones de preferencias y las respuestas ante validación, cancelación y fallo de guardado son concreciones aprobadas para L06. No eliminan otras posibilidades de edición cubiertas por FR-019.

El texto que estaba antes del separador era simplemente un borrador duplicado y mal formateado de los primeros 5 puntos. Al pegarlo, se mezclaron dos versiones (una en lista y otra en un solo párrafo).

  

Para hacerlo en menos de 20 minutos, la clave es ir directo al grano, usar viñetas simples y no dejar saltos de línea innecesarios. Aquí tienes la solución limpia, compacta y estructurada exactamente en los diez campos obligatorios:

  

Aquí tienes la descripción del caso de uso con un formato más limpio, profesional y con el nivel de detalle adecuado para un documento de ingeniería de software, basándonos estrictamente en el acta de acuerdos de tu repositorio.

  

### 6.1 Descripción detallada UC-05 · Actualizar perfil

**1. Identificador y nombre del caso de uso:** UC-05 Actualizar perfil.

  

**2. Objetivo:** Actualizar los datos personales, de contacto y las preferencias dietéticas del perfil propio, conservando los cambios de forma segura en el sistema.

  

**3. Participantes:**

  

- **Actor principal:** Usuario registrado.
    
      
    
- _(Nota: No hay actores de apoyo en este recorrido)_.
    
      
    

**4. Precondiciones:**

  

- El usuario dispone de una cuenta activa en la plataforma.
    
      
    
- El usuario tiene una sesión iniciada.
    
      
    
- _(Nota: La validez de los nuevos datos se comprueba durante el flujo de ejecución, no es una precondición)_.
    
      
    

**5. Inicio:** El usuario solicita actualizar su perfil desde la interfaz.

  

**6. Escenario principal de éxito:**

  

1. El usuario solicita actualizar su perfil.
    
      
    
2. El sistema presenta los datos actuales y distingue visualmente los **valores editables** (nombre completo, teléfono, dirección postal, preferencias dietéticas) de los **valores fijos** (alias, correo electrónico).
    
      
    
3. El usuario modifica los valores permitidos según sus necesidades.
    
      
    
4. El usuario solicita guardar los cambios.
    
      
    
5. El sistema comprueba que los datos introducidos cumplen con las reglas de validación (por ejemplo, nombre y teléfono no pueden quedar vacíos; el teléfono debe mantener el formato de registro).
    
      
    
6. El sistema guarda conjuntamente todos los cambios en el perfil.
    
      
    
7. El sistema confirma al usuario que la actualización se ha realizado con éxito.
    
      
    

**7. Extensiones (flujos alternativos):**

  

- **5.a. Falta un dato obligatorio o un dato no cumple su formato:**
    
      
    1. El sistema identifica los campos afectados y explica claramente la corrección necesaria.
        
          
        
    2. El sistema conserva los valores introducidos en la pantalla y no guarda ningún cambio en la base de datos.
        
          
        
    3. El usuario corrige los datos señalados.
        
          
        
    4. El flujo retorna al paso 4 (solicitud de guardado).
        
          
        
- ***.a. El usuario cancela la operación (en cualquier momento antes de guardar):**
    
      
    1. El sistema descarta los cambios realizados durante la edición actual.
        
          
        
    2. El perfil conserva los valores que estaban guardados anteriormente.
        
          
        
    3. El caso de uso termina sin realizar ninguna actualización.
        
          
        
- **6.a. El sistema no puede completar el guardado (fallo técnico):**
    
      
    1. El sistema informa que ha ocurrido un problema y no confirma la actualización.
        
          
        
    2. Los datos guardados permanecen sin cambios, pero la interfaz conserva los valores introducidos para que el usuario no pierda su trabajo.
        
          
        
    3. El usuario decide reintentar el guardado (el flujo vuelve al paso 4) o decide cancelar la edición (el flujo continúa por la extensión *.a).
        
          
        

**8. Postcondiciones:**

  

- **Con éxito:** El perfil contiene los cambios guardados de forma conjunta y el usuario recibe la confirmación. El alias y el correo electrónico mantienen sus valores originales.
    
      
    
- **Sin éxito o con cancelación:** El perfil conserva los valores anteriores intactos. El sistema garantiza que no quede una actualización parcial guardada.
    
      
    

**9. Reglas y NFR pertinentes:**

  

- **FR-019:** Edición de información personal y preferencias, con exclusión estricta de modificación de alias y correo electrónico.
    
      
    
- **NFR-010:** Accesibilidad en los mensajes de validación y formularios.
    
      
    

**10. Preguntas abiertas:** No existen preguntas abiertas ni decisiones pendientes para el alcance descrito en este caso de uso.

  
