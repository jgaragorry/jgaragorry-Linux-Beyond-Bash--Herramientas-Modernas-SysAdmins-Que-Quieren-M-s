# 🧪 Módulo 4 - Ejercicios comparativos: `dog`, `ripgrep`, `gdu`, `fzf`

Este documento presenta ejercicios prácticos para cada herramienta del **Módulo 4** del curso **Shell Evolved**, comparando su funcionalidad con comandos clásicos y destacando sus beneficios reales desde consola TTY.

---

## 🐶 1. DOG – Cliente DNS moderno

### 🌐 Ejercicio 1: Resolver un nombre de dominio
```bash
dog google.com
```
- 🎯 Objetivo: Obtener respuesta DNS clara y estructurada
- 🔁 Clásico: `dig google.com`
- ✅ Beneficio: Formato más limpio, colores, salida ordenada

---

### 🔄 Ejercicio 2: Consultar solo registros A y CNAME
```bash
dog google.com A CNAME
```
- 🎯 Objetivo: Filtrar tipos de registros DNS
- 🔁 Clásico: `dig google.com ANY`
- ✅ Beneficio: Precisión y claridad en la salida

---

## 🔍 2. RIPGREP (`rg`) – Búsqueda de texto ultrarrápida

### 📁 Ejercicio 1: Buscar “error” en todos los logs
```bash
rg error /var/log
```
- 🎯 Objetivo: Buscar coincidencias rápidamente en múltiples archivos
- 🔁 Clásico: `grep -r error /var/log`
- ✅ Beneficio: Mucho más rápido, salida colorida, sin necesidad de opciones complejas

---

### 📌 Ejercicio 2: Buscar coincidencias exactas
```bash
rg -F "ssh" /etc/ssh/sshd_config
```
- 🎯 Objetivo: Evitar expresiones regulares, mejorar precisión
- 🔁 Clásico: `grep -F ssh ...`
- ✅ Beneficio: Simpleza sin perder poder

---

## 💾 3. GDU – Diagnóstico visual del uso de disco

### 📊 Ejercicio 1: Analizar `/var` visualmente
```bash
gdu /var
```
- 🎯 Objetivo: Detectar carpetas pesadas con visualización jerárquica
- 🔁 Clásico: `du -h --max-depth=1 /var`
- ✅ Beneficio: Interfaz clara, navegación por teclado, más velocidad

---

### 🚫 Ejercicio 2: Excluir carpetas en el análisis
```bash
gdu --exclude /var/cache
```
- 🎯 Objetivo: Evitar carpetas irrelevantes en el resultado
- 🔁 Clásico: `du` con `--exclude` (no siempre disponible)
- ✅ Beneficio: Flexibilidad avanzada desde CLI

---

## 🔎 4. FZF – Exploración fuzzy interactiva

### 🧠 Ejercicio 1: Buscar un archivo por nombre parcial
```bash
find . -type f | fzf
```
- 🎯 Objetivo: Filtrar rápidamente archivos por coincidencia parcial
- 🔁 Clásico: `find . -type f | grep nombre`
- ✅ Beneficio: Interacción inmediata, sin saber nombre exacto

---

### ⌨️ Ejercicio 2: Buscar en historial de comandos
```bash
history | fzf
```
- 🎯 Objetivo: Reutilizar comandos sin recordar número de línea
- 🔁 Clásico: `history | grep ssh`
- ✅ Beneficio: Reutilización instantánea del historial

---

✅ Con estos ejercicios, los usuarios podrán dominar herramientas de diagnóstico modernas que mejoran la velocidad, legibilidad y control en tareas de administración diaria.

Siguiente archivo 👉 `modulo4-script-automatizacion.md`
