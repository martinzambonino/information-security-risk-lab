# Mapeo NIST CSF v1.1 — Sistema web hipotético

**Scope:** Sistema web con autenticación, base de datos, exposición a internet.
**Framework:** NIST Cybersecurity Framework v1.1
**Datos:** Completamente sintéticos. No corresponden a ningún sistema real.

## Funciones y categorías

### IDENTIFY (ID)

| Subcategoría | Descripción | Estado | Evidencia / Control |
| --- | --- | --- | --- |
| ID.AM-1 | Inventario de dispositivos físicos | ✅ Implementado | VPS único, IP fija documentada |
| ID.AM-2 | Inventario de software y plataformas | ✅ Implementado | `requirements.txt` + Dependabot |
| ID.RA-1 | Identificación de vulnerabilidades | 🔄 Parcial | Matriz de riesgo NIST 800-30 completada |
| ID.RA-3 | Amenazas internas y externas analizadas | 🔄 Parcial | 5 riesgos en `risk_matrix_web_system.md` |

### PROTECT (PR)

| Subcategoría | Descripción | Estado | Evidencia / Control |
| --- | --- | --- | --- |
| PR.AC-1 | Gestión de identidades y credenciales | ✅ Implementado | Ed25519 SSH key, sin contraseñas |
| PR.AC-3 | Gestión de acceso remoto | ✅ Implementado | Fail2ban + puerto no estándar |
| PR.DS-1 | Datos en reposo protegidos | ✅ Implementado | Solo datos sintéticos, sin PII |
| PR.DS-2 | Datos en tránsito protegidos | 🔄 Pendiente | TLS 1.3 + HSTS (control propuesto R-05) |
| PR.IP-1 | Baseline de configuración | 🔄 Parcial | `PermitRootLogin no`, Dependabot activo |

### DETECT (DE)

| Subcategoría | Descripción | Estado | Evidencia / Control |
| --- | --- | --- | --- |
| DE.AE-1 | Baseline de actividad de red establecida | ❌ Pendiente | No implementado en alcance educativo |
| DE.CM-1 | Red monitorizada para detectar eventos | 🔄 Parcial | `log_analyzer.py` detecta fuerza bruta SSH |
| DE.CM-7 | Monitoreo de personal, conexiones y dispositivos | ❌ Pendiente | Fuera del alcance del laboratorio |

### RESPOND (RS)

| Subcategoría | Descripción | Estado | Evidencia / Control |
| --- | --- | --- | --- |
| RS.RP-1 | Plan de respuesta ejecutado durante o después | ❌ Pendiente | Fuera de alcance — trabajo futuro |
| RS.CO-2 | Incidentes reportados a partes interesadas | ❌ Pendiente | Fuera de alcance |

### RECOVER (RC)

| Subcategoría | Descripción | Estado | Evidencia / Control |
| --- | --- | --- | --- |
| RC.RP-1 | Plan de recuperación ejecutado | ❌ Pendiente | Fuera de alcance — trabajo futuro |

## Leyenda de estados

- ✅ **Implementado:** Control activo y verificable
- 🔄 **Parcial:** En progreso o con limitaciones documentadas
- ❌ **Pendiente:** Identificado pero fuera del alcance actual
