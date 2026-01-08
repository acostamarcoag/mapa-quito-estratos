# Mapa de Estratificación Socioeconómica por Sector Censal — Distrito Metropolitano de Quito (DMQ)

Este repositorio presenta un **mapa interactivo de estratificación socioeconómica a nivel de sector censal** para el Distrito Metropolitano de Quito (DMQ). Es un ejercicio aplicado construido con **QGIS** (exportación web con **qgis2web/Leaflet**) y un flujo de preparación de datos apoyado en **SQL Server**.

El objetivo es **leer la realidad territorial desde el sector censal** (unidad técnica de análisis) y representar de forma comparable categorías socioeconómicas basadas en variables de vivienda, servicios, equipamiento del hogar, educación y condiciones laborales, siguiendo como referencia la **Metodología de Estratificación Socioeconómica del INEC (2011)**.

Mapa interactivo (GitHub Pages):  
https://acostamarcoag.github.io/mapa-quito-estratos/

---

## Qué es este proyecto (en una frase)
Una herramienta de **análisis territorial** que permite explorar **patrones socioeconómicos por sector censal** en el DMQ para apoyar decisiones en el sector **privado**, **público** y **social**.

---

## Para qué sirve (uso práctico)
Este ejercicio busca aportar evidencia para:

**1) Sector privado**
- Identificar **perfil socioeconómico potencial de demanda** por zonas.
- Apoyar decisiones sobre **ubicación de comercios/servicios** y tipos de oferta.
- Priorizar áreas para campañas, logística, expansión o segmentación territorial.

**2) Sector público y social**
- Orientar diagnósticos de **desigualdad territorial** y brechas de acceso.
- Apoyar focalización de **intervenciones, inversión y mejoras urbanas**.
- Identificar sectores con mayor vulnerabilidad relativa para planificación y seguimiento.

**Objetivo macro (a futuro):** escalar el enfoque y presentar resultados **a nivel nacional**, manteniendo comparabilidad metodológica.

---

## Unidad de análisis: sector censal (definición técnica)
El **sector censal** es una unidad territorial de levantamiento/organización de información censal. Trabajar a este nivel permite:
- Mayor detalle espacial que parroquia o cantón.
- Mejor aproximación a la heterogeneidad intraurbana.
- Lectura de “micro-territorios” útiles para planificación y mercado.

---

## Categorías de estratificación (5 niveles) y qué significa cada una

Este proyecto utiliza una escala de **cinco categorías**:

- **A (Alto):** sectores con mejores condiciones relativas de vivienda, acceso a servicios, equipamiento del hogar y capital humano.  
- **B (Medio alto):** condiciones favorables y estables; acceso a servicios y equipamiento por encima del promedio territorial.  
- **C+ (Medio):** condiciones intermedias; desempeño heterogéneo, con fortalezas y brechas puntuales.  
- **C- (Medio bajo):** condiciones por debajo del promedio; mayores limitaciones en vivienda/servicios/equipamiento o inserción laboral.  
- **D (Bajo):** sectores con mayores carencias relativas; limitaciones más marcadas en infraestructura del hogar, servicios y condiciones socioeconómicas.

**Importante:** la interpretación anterior es **analítica y divulgativa** para lectura territorial. Esta primera versión es un ejercicio exploratorio y **no sustituye** clasificaciones oficiales del INEC.

---

## Datos y variables consideradas (base metodológica INEC 2011)

La estratificación se apoya en un esquema de **variables con puntajes** (scoring) que aproximan condiciones socioeconómicas del hogar. En la capa publicada se integran campos como:

- `sec_hogares` (hogares del sector)
- `sec_puntaje_prom` (puntaje promedio del sector)
- `sec_estrato_sector` (categoría A/B/C+/C-/D)

A continuación se detallan las variables consideradas en este ejercicio y su estructura de puntajes (según la referencia metodológica 2011 y la implementación aplicada en el proyecto).

---

## Variables de vivienda (V)

### Tipo de vivienda

- Material predominante del techo o cubierta
- Estado del techo o cubierta
- Material predominante de las paredes exteriores
- Estado de las paredes exteriores
- Material predominante del piso
- Estado del piso
- Servicio higiénico de la vivienda
---
## Variables del hogar (H) — servicios y equipamiento

## Variables de educación y trabajo (P) — capital humano e inserción laboral
- Nivel de instrucción más alto al que asiste o asistió
- Obtuvo título en el nivel indicado
  
### Uso de TIC (últimos 3 meses)
### Actividad/ocupación (clasificaciones)
- **Ocupación o tarea:** según CIUO Rev. 08  
- **Actividad económica:** según CIIU 04

### Categoría de ocupación

- Aporta actualmente

### Estado conyugal

### Número de hijas e hijos vivos actualmente
- Rango: 0 a 20 (99 = No sabe)

### GRUPO1 — Grupo de ocupación (nivel 1)

---

## Campos visibles en el mapa (atributos principales)
Dependiendo de la exportación, la capa puede incluir:
- `sec` / `sec_id`: identificadores del sector censal.
- `sec_hogares`: número de hogares del sector.
- `sec_puntaje_prom`: puntaje promedio (agregado) del sector.
- `sec_estrato_sector`: categoría final (A, B, C+, C-, D).
- `parroquia`: código o referencia parroquial asociada.

---

## Implementación técnica (resumen)
- Preparación y consolidación de variables/puntajes: **SQL Server**.
- Integración espacial y simbología: **QGIS**.
- Exportación web: **qgis2web (Leaflet)**.
- Publicación: **GitHub Pages** (rama `main`, carpeta `/ (root)`).

---

## Estado del proyecto y hoja de ruta
**Versión actual:** primera versión exploratoria y aplicada.

**Siguiente etapa (dashboard):**
- Tarjetas resumen: hogares por categoría y porcentajes.
- Filtros: seleccionar categoría (A/B/C+/C-/D) y mostrar parroquias/sectores asociados.
- Listados dinámicos: “parroquias con mayor concentración por categoría”.
- Indicadores territoriales: ranking de sectores por puntaje promedio.

---

## Limitaciones y consideraciones
- Este es un ejercicio de análisis territorial basado en una referencia metodológica.  
- Los resultados **no reemplazan** productos oficiales del INEC.  
- La interpretación “A–D” es para lectura comparativa y comunicación pública del patrón territorial.

---

## Licencia
Este repositorio se publica bajo la licencia definida en el archivo `LICENSE`.

---

## Autor
Eco. Marco Antonio Acosta  
Quito, Ecuador
