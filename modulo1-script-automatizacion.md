# 🧪 Módulo 1 - Ejercicios comparativos: `exa`, `bat`, `dust`, `duf`

Este documento contiene ejercicios prácticos detallados para cada comando moderno del Módulo 1 del curso “Shell Evolved”. Cada ejercicio incluye:
- Objetivo
- Comando tradicional vs comando moderno
- Diferencias y beneficios claros
- Escenario donde es útil

> Todos los comandos son ejecutables desde TTY o terminal sin entorno gráfico (Ubuntu Server 24.04 LTS).

---

## 🟡 1. EXA – Reemplazo moderno de `ls`

### 🧭 Ejercicio 1: Listado detallado con colores y permisos
```bash
exa -la
```
- 🎯 Objetivo: Ver archivos ocultos y permisos con colores intuitivos
- 🔁 Comando tradicional: `ls -la`
- ✅ Beneficio: Mejor visibilidad de permisos, tamaños, y fechas
- 📌 Escenario: Auditoría de archivos en `/etc`, `/var/log`, etc.

---

### 🌳 Ejercicio 2: Mostrar árbol de directorios
```bash
exa -T /etc --level=2
```
- 🎯 Objetivo: Ver estructura jerárquica de configuración
- 🔁 Comando tradicional: `ls` + `tree` (si está instalado)
- ✅ Beneficio: No requiere herramienta adicional
- 📌 Escenario: Navegar configuraciones complejas (ej. `/etc/apache2`)

---

### 🕒 Ejercicio 3: Ordenar archivos por fecha de modificación
```bash
exa -l --sort=modified --icons
```
- 🎯 Objetivo: Detectar archivos modificados recientemente
- 🔁 Comando tradicional: `ls -lt`
- ✅ Beneficio: Añade íconos, más intuitivo visualmente
- 📌 Escenario: Detección de cambios recientes o anómalos

---

## 🔵 2. BAT – Reemplazo moderno de `cat`

### 📄 Ejercicio 1: Leer archivo con numeración y colores
```bash
bat /etc/fstab
```
- 🎯 Objetivo: Leer archivos de configuración con claridad
- 🔁 Comando tradicional: `cat /etc/fstab`
- ✅ Beneficio: Resaltado de sintaxis + numeración de líneas
- 📌 Escenario: Revisión rápida de archivos sin abrir editores

---

### 🔍 Ejercicio 2: Ver logs con paginación y resaltado
```bash
bat /var/log/syslog | less
```
- 🎯 Objetivo: Revisar logs de sistema con enfoque visual
- 🔁 Comando tradicional: `less /var/log/syslog`
- ✅ Beneficio: Más legible, útil para encontrar errores visualmente
- 📌 Escenario: Diagnóstico de eventos recientes del sistema

---

### 🧠 Ejercicio 3: Forzar resaltado de sintaxis
```bash
bat --language=ini /etc/fstab
```
- 🎯 Objetivo: Aplicar resaltado aunque la extensión no sea reconocida
- 🔁 Comando tradicional: No disponible en `cat`
- ✅ Beneficio: Visual uniforme, útil para logs, scripts, etc.
- 📌 Escenario: Configs personalizadas o sin extensión

---

## 🟣 3. DUST – Visualización moderna de uso de disco

### 📦 Ejercicio 1: Ver uso de disco con profundidad en `/var`
```bash
dust -d 2 /var
```
- 🎯 Objetivo: Detectar subdirectorios con mayor uso de espacio
- 🔁 Comando tradicional: `du -h --max-depth=2 /var`
- ✅ Beneficio: Más rápido, colorido, alineado jerárquicamente
- 📌 Escenario: Análisis de crecimiento de logs

---

### 🚫 Ejercicio 2: Excluir carpetas específicas del análisis
```bash
dust --ignore-directory /home/usuario/descargas
```
- 🎯 Objetivo: Excluir carpetas grandes que no deben auditarse
- 🔁 Comando tradicional: `du` no permite exclusión directa sin `--exclude` (GNU only)
- ✅ Beneficio: Filtro simple e inmediato
- 📌 Escenario: Auditar `/home` sin contar carpetas multimedia

---

### 📊 Ejercicio 3: Comparar `du` vs `dust`
```bash
sudo du -sh /var && dust /var
```
- 🎯 Objetivo: Comparar resultados y velocidad
- 🔁 Comando tradicional: `du -sh /var`
- ✅ Beneficio: Más claro, ordenado por uso, visual
- 📌 Escenario: Diagnóstico de servidores con espacio lleno

---

## 🟢 4. DUF – Monitoreo visual de particiones

### 📍 Ejercicio único: Ver todas las particiones montadas
```bash
duf
```
- 🎯 Objetivo: Ver uso de disco por punto de montaje
- 🔁 Comando tradicional: `df -h`
- ✅ Beneficio: Tabla clara, con colores, porcentaje y nombre de dispositivos
- 📌 Escenario: Validar discos montados en VPS, contenedores, etc.

---

✅ Al completar estos ejercicios, el estudiante tendrá una visión clara de:
- Qué comandos modernos son útiles
- En qué contextos aplicarlos
- Cómo se comparan con sus equivalentes clásicos

Siguiente archivo 👉 `modulo1-script-automatizacion.md`
