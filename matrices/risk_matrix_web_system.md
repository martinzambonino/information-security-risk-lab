# Matriz de riesgo — Sistema web hipotético

**Alcance:** Sistema web con autenticación, base de datos PostgreSQL, hosting en VPS.
**Metodología:** NIST SP 800-30 Rev.1 — probabilidad × impacto.
**Datos:** Completamente sintéticos. No corresponden a ningún sistema real.

## Escala de valoración

| Nivel | Probabilidad | Impacto |
| --- | --- | --- |
| 1 | Raro (<10%) | Mínimo |
| 2 | Improbable (10–30%) | Menor |
| 3 | Posible (30–60%) | Moderado |
| 4 | Probable (60–80%) | Mayor |
| 5 | Casi seguro (>80%) | Crítico |

## Riesgos identificados

| ID | Amenaza | Activo afectado | Prob. | Impacto | Riesgo | Control propuesto |
| --- | --- | --- | --- | --- | --- | --- |
| R-01 | Fuerza bruta SSH | Servidor VPS | 4 | 5 | **20 — Crítico** | Fail2ban + Ed25519 + PermitRootLogin no |
| R-02 | Inyección SQL | Base de datos | 3 | 5 | **15 — Alto** | Prepared statements + validación de input |
| R-03 | Credenciales en repositorio | Código fuente | 3 | 4 | **12 — Alto** | .gitignore + pre-commit gitleaks |
| R-04 | Dependencias con CVE | Aplicación | 4 | 3 | **12 — Alto** | Dependabot + actualización semanal |
| R-05 | Sin cifrado en tránsito | Comunicación | 2 | 4 | **8 — Medio** | TLS 1.3 + HSTS |

## Tratamiento de riesgos críticos y altos

### R-01 — Fuerza bruta SSH

- Autenticación por clave Ed25519 únicamente, sin contraseñas
- Fail2ban: ban de 1 hora tras 3 intentos fallidos
- `PermitRootLogin no` en `/etc/ssh/sshd_config`
- Cambiar puerto SSH de 22 a puerto no estándar

### R-03 — Credenciales expuestas en repositorio

- Pre-commit hook con gitleaks antes de cada push
- Variables de entorno para todas las credenciales
- Secret Scanning + Push Protection habilitados en GitHub
- `.env.example` con placeholders como única referencia documentada
