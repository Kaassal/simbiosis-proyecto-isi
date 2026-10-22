# Acta de acuerdos de UC-21 · Buscar recetas

| Campo | Valor |
| --- | --- |
| Proyecto | Proyecto Simbiosis |
| Caso de uso | UC-21 · Buscar recetas |
| Estado | Vigente |
| Versión | 1.1 |
| Fecha de redacción | 10/10/2026 |
| Aprobación docente para L06 | 10/10/2026 |
| Tipo | Acta simulada de aclaración |
| Finalidad | Concretar el comportamiento que se describirá en L06. |

Esta acta recoge las respuestas que el analista habría obtenido al consultar a una persona usuaria. No documenta una entrevista real. El profesor ha aprobado las aclaraciones para L06. Complementan el catálogo canónico para el alcance seleccionado; no modifican su redacción.

## 1. Participantes y alcance

En la simulación participan un analista y una persona usuaria registrada. La persona quiere localizar una receta que cumpla sus criterios y consultar su detalle.

Las consultas descritas se realizan con una sesión iniciada. Se consideran la búsqueda por ingredientes, la búsqueda por una palabra o frase y la exclusión de ingredientes. La consulta del detalle forma parte de UC-21.

Los demás filtros, las recomendaciones, el historial, los favoritos y las acciones sobre la receta quedan fuera de esta aclaración. Sus requisitos siguen vigentes. No se aplica automáticamente un filtro de alergias del perfil.

## 2. Acuerdos

### Criterios de búsqueda

- La persona selecciona los ingredientes que desea encontrar. Una receta debe contener todos los ingredientes seleccionados para aparecer como resultado.
- La persona también puede seleccionar ingredientes que desea excluir. Ninguna receta de los resultados puede contener alguno de ellos.
- La selección se hace a partir de los nombres de ingredientes disponibles en el sistema. La persona puede añadir o retirar selecciones antes de buscar.
- Si se selecciona el mismo ingrediente para incluirlo y excluirlo, el sistema señala el conflicto. No ejecuta la búsqueda hasta que la persona lo corrija.
- La búsqueda por texto comprueba si la palabra o frase aparece en el título o en la descripción breve. Una frase debe aparecer seguida y en el mismo orden. No se distinguen mayúsculas ni tildes.
- Si se combinan texto, ingredientes incluidos e ingredientes excluidos, la receta debe cumplir todos los criterios.
- La persona debe indicar al menos un criterio. Si no indica ninguno, el sistema solicita un criterio y conserva la búsqueda sin ejecutar.

### Resultados y detalle

- Para estas consultas se consideran recetas publicadas y validadas. Las recetas pendientes de validación no aparecen.
- Los resultados se muestran por fecha de publicación, con las recetas más recientes primero.
- Cada vista previa muestra título, imagen, calificación promedio y descripción breve. Si falta la imagen, se indica «Sin imagen». Si no hay valoraciones, se indica «Sin valoraciones»; no se muestra un promedio de cero.
- Al seleccionar un resultado, la persona consulta el detalle de esa receta. El detalle muestra título, imagen si existe, ingredientes, instrucciones de preparación, tiempo de cocción, número de porciones, alias de quien la publicó e insignia de validación.
- La persona puede volver a los resultados. Se conservan los criterios y el orden de la última búsqueda.
- Para obtener otros resultados, la persona puede modificar los criterios y ejecutar otra búsqueda.

### Búsqueda sin resultados

- Si ninguna receta cumple los criterios, el sistema indica que no hay resultados para esa búsqueda. Conserva los criterios para que la persona pueda modificarlos.
- Si el texto admite una corrección ortográfica, el sistema propone esa corrección. En otro caso, propone alternativas relacionadas con los criterios cuando dispone de ellas. Si no dispone de sugerencias, lo indica.
- Las sugerencias se muestran separadas de los resultados. No se presentan como recetas que cumplen la búsqueda original.
- El sistema no cambia los criterios ni ejecuta otra búsqueda sin una acción de la persona. Si esta acepta una corrección o una alternativa, ve los criterios propuestos y decide si ejecuta la nueva búsqueda.
- Las sugerencias conservan los ingredientes excluidos. No se propone retirar una exclusión para conseguir resultados.
- La persona puede modificar los criterios por su cuenta o terminar la consulta.

### Fallo de la consulta

- Si el sistema no puede completar la búsqueda o cargar el detalle, informa del problema. No presenta el fallo como una búsqueda sin resultados.
- Se conservan los criterios de la última búsqueda. La persona puede reintentar la consulta o terminarla.

## 3. Fuentes y relación con los requisitos

| Fuente | Respaldo |
| --- | --- |
| [Catálogo canónico de requisitos](../requisitos/catalogo-requisitos.md), UR-08; FR-085, FR-086, FR-087, FR-089, FR-099, FR-102 y FR-119 | Texto, ingredientes, exclusiones, vistas previas, orden por fecha, ayuda sin resultados y acceso a búsqueda avanzada. |
| Mismo catálogo, FR-056, FR-066 y FR-192 | Datos de una receta, insignia de validación e identidad pública mediante alias. |
| [Plan de E2](../planificacion/plan-iteracion-e2.md), apartado 4.4 | Recorrido de búsqueda, resultados y consulta del detalle. |

La combinación concreta de criterios, la coincidencia del texto, la selección de recetas visibles, el orden inicial y las respuestas ante conflictos, ausencia de datos y fallos son concreciones aprobadas para L06. FR-102 respalda la ayuda cuando no hay resultados, aunque no figure en la selección inicial de FR del plan de E2.


### 6.2 Descripción de un caso

**6.2 Descripción detallada UC-21 · Buscar recetas**

  

**1. Identificador y nombre del caso de uso:** UC-21 Buscar recetas. 

**2. Objetivo:** Buscar recetas mediante los criterios seleccionados, consultar los resultados y acceder al detalle de una receta. 

**3. Participantes:** Actor principal: Usuario registrado.

**4. Precondiciones:** El usuario tiene una sesión iniciada. 

**5. Inicio:** El usuario se dispone a buscar recetas especificando sus criterios.

  

**6. Escenario principal de éxito:**
1. El usuario selecciona al menos un criterio de búsqueda (palabra o frase, ingredientes a incluir y/o ingredientes a excluir).
    
      
    
2. El usuario solicita ejecutar la búsqueda.
    
      
    
3. El sistema verifica que no existan conflictos entre los criterios.
    
      
    
4. El sistema obtiene las recetas publicadas y validadas que cumplen todos los criterios combinados.
    
      
    
5. El sistema presenta los resultados ordenados por fecha de publicación (las más recientes primero), mostrando una vista previa de cada receta (título, imagen o «Sin imagen», calificación promedio o «Sin valoraciones» y descripción breve).
    
      
    
6. El usuario selecciona un resultado de la lista.
    
      
    
7. El sistema muestra el detalle de la receta seleccionada (título, imagen, ingredientes, instrucciones de preparación, tiempo de cocción, número de porciones, alias del autor e insignia de validación).
    
      
    

**7. Extensiones (flujos alternativos):**

  

- **2.a. Ausencia de criterios:**
    
      
    1. El sistema detecta que no se indicó ningún criterio.
        
          
        
    2. El sistema solicita al usuario que indique al menos un criterio y conserva la búsqueda sin ejecutar.
        
          
        
    3. El flujo vuelve al paso 1.
        
          
        
- **3.a. Conflicto de criterios (mismo ingrediente a incluir y excluir):**
    
      
    1. El sistema señala el conflicto al usuario.
        
          
        
    2. El sistema no ejecuta la búsqueda hasta que el usuario corrija el error.
        
          
        
    3. El flujo vuelve al paso 1.
        
          
        
- **4.a. Búsqueda sin resultados:**
    
      
    1. El sistema indica que no hay resultados para esa búsqueda y conserva los criterios.
        
          
        
    2. El sistema propone una corrección ortográfica o sugerencias alternativas relacionadas, mostrándolas separadas de los resultados y conservando las exclusiones. Si no dispone de sugerencias, lo indica.
        
          
        
    3. El usuario puede aceptar una sugerencia, modificar los criterios (vuelve al paso 1) o terminar la consulta.
        
          
        
- **4.b. Fallo técnico de la consulta o detalle:**
    
      
    1. El sistema informa del problema sin presentarlo como una búsqueda sin resultados.
        
          
        
    2. El sistema conserva los criterios de la última búsqueda.
        
          
        
    3. El usuario puede reintentar la consulta (vuelve al paso 2) o terminarla.
        
          
        
- **7.a. El usuario vuelve a los resultados o modifica la búsqueda:**
    
      
    1. El usuario solicita volver atrás desde el detalle de la receta.
        
          
        
    2. El sistema muestra nuevamente la lista, conservando los criterios y el orden de la última búsqueda.
        
          
        
    3. El usuario puede modificar los criterios y ejecutar otra búsqueda (vuelve al paso 1).
        
          
        

**8. Postcondiciones:**

  

- **Con éxito:** El usuario visualiza el detalle de la receta seleccionada.
    
      
    
- **Sin éxito o con cancelación:** El usuario recibe un aviso sobre la falta de resultados o el fallo de la consulta. Al ser una consulta, los datos de la plataforma permanecen sin cambios.
    
      
    

**9. Reglas y NFR pertinentes:** UR-08; FR-056, FR-066, FR-085, FR-086, FR-087, FR-089, FR-099, FR-102, FR-119 y FR-192. NFR-004, NFR-005 y NFR-010. 

**10. Preguntas abiertas:** No hay preguntas abiertas para el alcance descrito.

  

