# Proyecto Simbiosis

| Versión | Fecha      | Estado   |
| ------- | ---------- | -------- |
| 2.4     | 29/10/2026 | Borrador |

**Documentos de referencia:** 
* Acta de acuerdos de UC-21
* Catálogo de requisitos (UR-08, FR-085, FR-086, FR-087, FR-102)

## Épica de búsqueda (UC-21)
**Como** usuario registrado, **quiero** buscar recetas combinando texto, ingredientes incluidos e ingredientes excluidos, **para** encontrar opciones que se ajusten exactamente a mis preferencias y restricciones alimentarias.
* **Estado:** Descompuesta en US-01, US-02 y US-03.
* **Justificación de la división:** La división separa los tres métodos de filtrado principales, ya que cada uno aporta valor independiente y puede utilizarse por sí solo. Esto permite construir y validar de forma gradual el motor de búsqueda, asegurando primero la coincidencia de texto y luego la lógica de conjuntos (inclusión/exclusión).

## Historias de usuario

### US-01: Buscar mediante palabra o frase
**Como** usuario registrado, **quiero** buscar recetas introduciendo una palabra o frase, **para** localizar rápidamente platos concretos por su título o descripción.
* **Trazabilidad:** UR-08, UC-21, FR-085. Acta UC-21 (Criterios de búsqueda, Búsqueda sin resultados).
* **Criterios de aceptación:**
  1. **Coincidencia del texto:** Dado que existen recetas validadas con la frase "tarta de manzana" en su título o descripción, cuando introduzco "tarta de manzana" como criterio, entonces el sistema muestra esas recetas en los resultados.
  2. **Independencia de formato:** Dado que existe una receta llamada "TARTA", cuando introduzco la palabra "tarta" en minúsculas y sin tildes, entonces el sistema devuelve esa receta en los resultados sin distinguir mayúsculas ni acentos.
  3. **Búsqueda sin resultados:** Dado que no hay recetas que contengan la palabra "unicornio", cuando ejecuto la búsqueda con ese texto, entonces el sistema indica que no hay resultados y conserva la palabra introducida.

### US-02: Buscar por ingredientes incluidos
**Como** usuario registrado, **quiero** buscar recetas especificando una lista de ingredientes a incluir, **para** encontrar platos que pueda preparar con los alimentos que ya tengo disponibles.
* **Trazabilidad:** UR-08, UC-21, FR-086. Acta UC-21 (Criterios de búsqueda, Resultados y detalle).
* **Criterios de aceptación:**
  1. **Inclusión de todos los ingredientes:** Dado que he seleccionado los ingredientes "tomate" y "queso", cuando ejecuto la búsqueda, entonces el sistema devuelve únicamente las recetas que contienen "tomate" y "queso" simultáneamente.
  2. **Búsqueda combinada:** Dado que he introducido el texto "ensalada" y seleccionado el ingrediente "atún", cuando ejecuto la búsqueda, entonces el sistema devuelve únicamente las recetas que incluyen "atún" y contienen la palabra "ensalada" en el título o descripción.
  3. **Control de criterios vacíos:** Dado que no se ha indicado ningún criterio de búsqueda, cuando intento ejecutar la consulta, entonces el sistema solicita indicar al menos un criterio y conserva la búsqueda sin ejecutarla.

### US-03: Excluir ingredientes de la búsqueda
**Como** usuario registrado, **quiero** especificar ingredientes que deseo excluir de los resultados, **para** evitar recetas que contengan alimentos que no me gustan o que no puedo consumir.
* **Trazabilidad:** UR-08, UC-21, FR-087. Acta UC-21 (Criterios de búsqueda).
* **Criterios de aceptación:**
  1. **Exclusión de cualquiera de los seleccionados:** Dado que he seleccionado excluir los ingredientes "nuez" y "almendra", cuando ejecuto la búsqueda, entonces ninguna de las recetas de los resultados contiene "nuez" ni "almendra" entre sus ingredientes.
  2. **Conflicto de inclusión y exclusión:** Dado que he seleccionado el ingrediente "leche" tanto como ingrediente a incluir como ingrediente a excluir, cuando intento buscar, entonces el sistema señala el conflicto y no ejecuta la búsqueda hasta que se modifique la selección.
  3. **Exclusión independiente:** Dado que selecciono excluir "ajo" sin indicar texto ni ingredientes a incluir, cuando ejecuto la consulta, entonces el sistema devuelve todas las recetas validadas de la plataforma que no contienen el ingrediente "ajo".

## Revisión INVEST

| Comprobación | Aplicada | Cumple | Justificación |
| :--- | :---: | :---: | :--- |
| **Independiente** | Sí | Sí | Cada historia aporta un método de filtrado que puede implementarse y arrojar un resultado útil sin depender estrictamente de que los demás filtros ya estén programados. |
| **Negociable** | Sí | Sí | Expresan la necesidad de filtrado pero dejan margen para que el equipo decida la interfaz técnica respetando los acuerdos del acta. |
| **Valiosa** | Sí | Sí | Cada historia detalla un beneficio directo para el usuario: aprovechar lo que tiene (US-02), evitar lo que le hace daño (US-03) o ir directo a un antojo (US-01). |
| **Estimable** | Sí | Sí | Los escenarios de éxito, fallo, combinaciones y conflictos están claros en los criterios, lo que permite al equipo estimar la complejidad de las consultas en base de datos. |
| **Pequeña** | Sí | Sí | Dividen la función general de búsqueda en tres parámetros lógicos manejables (texto, inclusión, exclusión). |
| **Comprobable** | Sí | Sí | Los nueve criterios incluyen situaciones de partida concretas y resultados del sistema observables, independientes del diseño visual. |

**Nota tras la revisión INVEST:**
Se han modificado los criterios de aceptación para ajustarlos a las observaciones del Notebook de revisión. En US-01 se han retirado la mención a sugerencias ortográficas alternativas y el ordenamiento por fecha para asegurar la trazabilidad estricta. En US-02 (Criterio 3) y US-03 (Criterio 2) se han reescrito los escenarios para eliminar referencias a elementos específicos de la interfaz (como "pantallas" o "listas"), garantizando que las historias describan el comportamiento de forma totalmente independiente de las decisiones de diseño visual.