# Reporte de Ciclo 27 - BaldeCash

**Periodo:** 24 de Noviembre - 30 de Noviembre, 2025

---

## Resumen Ejecutivo

| Metrica | Valor |
|---------|-------|
| Issues al inicio | 57 |
| Issues agregados | 7 |
| Issues completados | 6 |
| Issues totales al final | 64 |
| Ratio de exito | 9.4% |
| Scope completado | 16 puntos |
| Scope total | 153 puntos |

---

## Issues Completados

### Por Estado

| Issue | Titulo | Asignado | Solicitante | Estado |
|-------|--------|----------|-------------|--------|
| BAL-660 | Correcciones frontend pagar cuotas | - | Lidymar Dellen | Done |
| BAL-659 | Corregir automatizacion HP en make | - | Marco Del Rio | Done |
| BAL-638 | Permitir pagar solicitudes | - | Yadira Yovera | Done |
| BAL-639 | Corregir faltas ortograficas | - | Marco Del Rio | Done |
| BAL-642 | Nuevo boton campana Voximplant | - | Yadira Yovera | Done |
| BAL-648 | Revisar scroll pagar cuotas ZE | - | Yosmar Cardenas | Done |

### Bugs Resueltos

| Issue | Titulo | Descripcion |
|-------|--------|-------------|
| BAL-646 | Bug direccion ubigeo | Problema con direccion y ubigeo |
| BAL-645 | Bug solicitud 86230 | Error en solicitud especifica |

### Integraciones

| Issue | Titulo | Integracion |
|-------|--------|-------------|
| BAL-657 | storeBulk para prestamos | Importacion masiva Excel |
| BAL-656 | Endpoint QR sandbox | Banco BBVA |
| BAL-655 | Autenticacion BBVA QR | BBVA |

### Marketing/UX

| Issue | Titulo | Solicitante |
|-------|--------|-------------|
| BAL-654 | Cambios landings marketing | Patio Digital |
| BAL-653 | Cambios UX/UI Pamela | Pamela Marketing |

---

## Hotfixes del Ciclo

Commits identificados como correcciones urgentes:

| Proyecto | Commit | Descripcion |
|----------|--------|-------------|
| webservice | fix: excluir solicitudes | Exclusion de solicitudes en procesos |
| webservice | fix: usar modelo Landing | Correccion modelo de datos |
| webservice | fix: cambiar SKU | Ajuste de SKU en productos |
| pidetuprestamo | fix: cambios marketing | Ajustes de marketing |

---

## Commits con Asistencia de IA (Claude Code)

Durante este ciclo se utilizó Claude Code para asistir en el desarrollo:

| Proyecto | Commit | Autor |
|----------|--------|-------|
| webservice | feat: endpoint importar prestamos Excel | Leonardo Medina |
| webservice | feat: tabla exclusion Absolute | Leonardo Medina |
| webservice | feat: campaign-segundo | Leonardo Medina |
| webservice | chore: multiple improvements | Leonardo Medina |

**Total commits con Claude Code:** 13+

---

## Metricas por Solicitante

| Solicitante | Issues Completados |
|-------------|-------------------|
| Lidymar Dellen | 1 |
| Marco Del Rio | 2 |
| Yadira Yovera | 2 |
| Yosmar Cardenas | 1 |
| Vania Hagel | 1 |
| Patio Digital | 1 |
| Pamela Marketing | 1 |
| BBVA | 2 |
| Bug Reports | 2 |

---

## Sentry - Errores Reportados

**Total de errores en el periodo:** 50

### Tipos de Error Principales

| Tipo | Cantidad | Proyecto |
|------|----------|----------|
| OAuthServerException | ~20 | webservice |
| NavigationDuplicated | ~15 | pidetuprestamo-bc |
| Redirect Errors | ~10 | varios |
| Otros | ~5 | varios |

### Recomendaciones

1. **OAuthServerException**: Revisar manejo de credenciales y tokens expirados
2. **NavigationDuplicated**: Implementar guards en router de Vue
3. **Redirect Errors**: Validar rutas y estados de sesion

---

## Progreso del Ciclo

```
Dia 1 (Lun): 57 issues, 2 completados
Dia 2 (Mar): 57 issues, 2 completados
Dia 3 (Mie): 57 issues, 2 completados
Dia 4 (Jue): 63 issues, 6 completados
Dia 5 (Vie): 64 issues, 6 completados
Dia 6 (Sab): 64 issues, 6 completados
Dia 7 (Dom): 64 issues, 6 completados
```

---

## Proyectos GitLab Activos

1. **webservice** (ID: 19216142) - Backend principal
2. **pidetuprestamo** (ID: 19193800) - Landing pages
3. **admin** (ID: 19252249) - Panel administrativo
4. **zonaclientes** (ID: 35770608) - Zona de clientes

---

## Conclusiones

- El ciclo tuvo una tasa de completacion del **9.4%** (6 de 64 issues)
- Se resolvieron **2 bugs criticos** relacionados con ubigeo y solicitudes
- Se avanzó en la **integracion con BBVA** para pagos QR
- **13+ commits** fueron asistidos por Claude Code
- Se identificaron **50 errores** en Sentry que requieren atencion

---

*Generado automaticamente el 1 de Diciembre, 2025*
