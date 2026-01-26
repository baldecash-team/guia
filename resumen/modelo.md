# Modelo de Reporte de Ciclo - BaldeCash

Basado en: `modelo.html`

---

## 1. Header (Encabezado)
Muestra el numero del ciclo actual con el rango de fechas del sprint (ej: "19 Ene 2026 - 26 Ene 2026"). Incluye navegacion lateral para ir al ciclo anterior, siguiente o al indice principal. El fondo usa el color corporativo #262877 con texto blanco. Los botones de navegacion tienen efecto hover y el ciclo siguiente se deshabilita si no existe.

---

## 2. Sidebar Flotante (Navegacion)
Menu lateral izquierdo que aparece al hacer hover, con enlaces ancla a todas las secciones del reporte. Agrupa las secciones en categorias: Issues, Codigo, Calidad y Detalles. Usa iconos de puntos de colores para cada enlace y tiene scroll si el contenido excede la altura visible. El icono de hamburguesa aparece cuando el sidebar esta oculto.

---

## 3. KPIs Cards (Tarjetas de Metricas Principales)
Seis tarjetas horizontales mostrando: Issues Completados, Ratio de Exito (%), Commits GitLab, Commits GitHub, Total Commits y Claude Code (con %). Cada tarjeta tiene un icono distintivo con fondo de color y el valor principal en texto grande y bold. Los colores varian segun el tipo: verde para completados, naranja para GitLab, gris para GitHub, purpura para Claude. Las tarjetas tienen animacion fade-in escalonada y efecto hover con elevacion.

---

## 4. Resumen Ejecutivo
Tres columnas con tablas compactas: Issues (total, completados, in progress, pendientes, ratio), Commits GitLab (total, proyectos activos, desglose por repo), Commits GitHub (total, repos activos, desglose por repo). Proporciona una vista rapida de los numeros clave del ciclo sin necesidad de scroll. Usa formato de tabla con filas alternadas y valores alineados a la derecha. Es la primera seccion de contenido despues de los KPIs.

---

## 5. Observaciones y Recomendaciones
Tres cards de colores: verde para Aspectos Positivos, naranja para Areas de Mejora, azul para Acciones Sugeridas. Cada card tiene un icono circular, titulo y lista de 4-5 puntos con vinetas. Resume los hallazgos principales del ciclo en formato digerible para stakeholders. Los colores siguen el patron semaforo para comunicar rapidamente el estado.

---

## 6. Distribucion por Prioridad
Tabla con columnas: Prioridad (con emoji de color), Total issues, Completados y Porcentaje de exito. Incluye filas para Urgent, High, Medium, Low y Sin Prioridad con fila de totales al final. A la derecha muestra un grafico donut de Highcharts con la distribucion visual. Permite identificar si las tareas urgentes se completaron y cuales prioridades tienen menor ratio de exito.

---

## 7. Desglose por Owner
Tabla con columnas: Desarrollador, Done (verde), In Review (azul), Total y Ratio de exito. Muestra el rendimiento individual de cada miembro del equipo incluyendo "Sin asignar". Incluye grafico de barras horizontales al lado derecho para visualizacion rapida. La nota superior explica que el ratio incluye Done + In Review sobre el total asignado al ciclo.

---

## 8. Proyectos Linear
Cuatro KPI cards: Total Proyectos, In Progress, Completed y Sin Lead Asignado (resaltado en amarillo). Tabla de proyectos In Progress mostrando: Nombre, Lead asignado, Estado y Prioridad. Segunda seccion con grid de cards amarillas listando los proyectos que no tienen Lead asignado. Ayuda a identificar proyectos huerfanos que necesitan responsable.

---

## 9. Commits por Proyecto
Dos tablas lado a lado: GitLab (con icono naranja) y GitHub (con icono negro). Cada tabla muestra repositorio, cantidad de commits y porcentaje del total. Incluye fila de totales con fondo de color. Permite ver rapidamente donde se concentro la actividad de desarrollo.

---

## 10. Commits por Autor
Tabla unica consolidada con columnas: Autor, GitLab, GitHub, Total y Porcentaje. Muestra la contribucion de cada desarrollador en ambas plataformas. La fila de totales suma commits de ambas fuentes. Util para medir la distribucion de trabajo entre el equipo.

---

## 11. Lineas de Codigo por Autor (LOC)
Tres KPI cards grandes: Lineas anadidas (+verde), Lineas eliminadas (-rojo), Lineas netas (azul). Tabla por autor con columnas: +Anadidas, -Eliminadas y Neto. Segunda tabla por repositorio con los mismos campos, filas naranjas indican repos de GitHub. Grafico de barras al final comparando visualmente las contribuciones de cada autor.

---

## 12. Commits con Claude Code (AI-Assisted)
Banner explicativo purpura describiendo que son los commits asistidos por IA (marcadores: emoji robot, Co-Authored-By). Tres KPI cards: Commits con Claude, Total Commits y Tasa de Adopcion IA (%). Tabla desglosando GitLab vs GitHub con sus respectivos porcentajes de adopcion. Mide el uso de herramientas de IA en el proceso de desarrollo.

---

## 13. Hotfixes y Bugfixes del Ciclo
Banner azul explicando la diferencia entre hotfix y bugfix. Muestra un badge central verde/rojo segun el estado de estabilidad del ciclo. Cuatro KPI cards muestran: cantidad de hotfixes, bugfixes, total commits y tasa de correccion (%). Tabla detallada de bugfixes con fuente, proyecto, SHA, fecha, autor y mensaje.

**Criterios de deteccion:**

| Tipo | Definicion | Deteccion |
|------|------------|-----------|
| Hotfix | Correccion urgente en **produccion** | Rama: `hotfix/*`, `hot-fix/*`, `emergency/*`, `urgent-fix/*` |
| Bugfix | Correccion de bug en desarrollo normal | Mensaje: `fix:`, `fix()`, `bugfix:`, `bug:` |

**Estados posibles (segun hotfixes):**
- Verde (0 hotfixes): Ciclo estable
- Amarillo (1-2 hotfixes): Requiere atencion
- Rojo (3+ hotfixes): Revisar procesos de desarrollo

**Tabla de bugfixes:**
| # | Fuente | Proyecto | SHA | Fecha | Autor | Mensaje |

---

## 14. Sentry - Monitoreo de Errores
Tres KPI cards: Eventos de Error (rojo), Issues No Resueltos (verde) y Periodo Analizado (azul). Muestra las fechas exactas del periodo consultado con enlace directo a Sentry. Si no hay datos disponibles, muestra un banner amarillo de advertencia. Permite evaluar la estabilidad del sistema durante el ciclo.

---

## 15. Issues Completados
Tabla completa con todos los issues marcados como Done en el ciclo. Columnas: Issue (link a Linear), Titulo, Prioridad (emoji), Owner y Proyecto. Header verde para distinguir de otras tablas. Cada fila tiene efecto hover y el ID es clickeable para ver detalles en Linear.

---

## 16. Desglose por Solicitante
Tabla mostrando quien solicito cada issue con columnas: Solicitante, Cantidad de Issues y Porcentaje. Lista TODOS los solicitantes sin agrupar en "Otros" para visibilidad completa. Incluye fila para "Sin solicitante" cuando aplica. Fila de totales al final con suma y 100%.

---

## 17. Issues No Completados
Banner amarillo explicando que estos issues fueron movidos al siguiente ciclo. Tabla con columnas: Issue (link), Titulo, Estado actual (emoji + texto), Asignado y Solicitante. Estados posibles: Todo (amarillo), In Progress (azul), In Review (verde). Permite tracking de issues que no se terminaron y su estado actual.

---

## 18. Footer
Texto centrado indicando que el reporte fue generado automaticamente por Claude Code. Incluye el nombre del ciclo y rango de fechas. Fondo gris oscuro con texto claro. Boton flotante en esquina inferior derecha para scroll al inicio.

---

## Notas Tecnicas

### Tecnologias usadas:
- **Tailwind CSS** via CDN para estilos
- **Highcharts** para graficos (donut, barras)
- **Google Fonts** - Asap como tipografia principal

### Colores corporativos:
- Primario: `#262877` (azul oscuro)
- Secundario: `#3d3d99` (azul medio)

### Fuentes de datos:
- **Linear**: Issues, proyectos, ciclos, owners, solicitantes
- **GitLab API**: Commits por proyecto y autor
- **GitHub API**: Commits por repo y autor
- **Sentry API**: Eventos de error e issues

### Emojis de prioridad:
- Urgent: `&#128308;` (circulo rojo)
- High: `&#128992;` (circulo naranja)
- Medium: `&#128993;` (circulo amarillo)
- Low: `&#128994;` (circulo verde)
- Sin prioridad: `&#9898;` (circulo blanco)

### Variables del template:
```
{NUMERO}           - Numero del ciclo
{FECHA_INICIO}     - Fecha de inicio del ciclo
{FECHA_FIN}        - Fecha de fin del ciclo
{ANTERIOR}         - Numero del ciclo anterior
{SIGUIENTE}        - Numero del ciclo siguiente
{ISSUES_COMPLETADOS} - Cantidad de issues completados
{TOTAL_ISSUES}     - Total de issues en el ciclo
{RATIO_EXITO}      - Porcentaje de exito
{COMMITS_GITLAB}   - Commits de GitLab
{COMMITS_GITHUB}   - Commits de GitHub
{TOTAL_COMMITS}    - Total de commits
{CLAUDE_COMMITS}   - Commits con Claude Code
{CLAUDE_PERCENT}   - Porcentaje de adopcion IA
{HOTFIXES}         - Cantidad de hotfixes
{BUGFIXES}         - Cantidad de bugfixes
{TASA_CORRECCION}  - Porcentaje de correccion
{SENTRY_EVENTOS}   - Eventos de error en Sentry
{SENTRY_ISSUES}    - Issues no resueltos en Sentry
{LOC_ADDED}        - Lineas de codigo agregadas
{LOC_DELETED}      - Lineas de codigo eliminadas
{LOC_NET}          - Lineas netas
```

