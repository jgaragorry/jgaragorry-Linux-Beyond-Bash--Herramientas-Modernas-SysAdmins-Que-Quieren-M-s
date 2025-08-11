# 🧪 Módulo 3 - Ejercicios comparativos: `just`, `entr`, `zoxide`

Este documento contiene ejercicios prácticos para cada herramienta del **Módulo 3**, diseñados para demostrar cómo automatizar tareas, monitorear archivos y navegar más eficientemente en terminal.

> Todos los ejercicios son compatibles con Ubuntu Server 24.04 LTS y funcionan correctamente desde TTY o SSH.

---

## ⚙️ 1. JUST – Reemplazo moderno de `make` para tareas repetitivas

### 🔁 Ejercicio 1: Crear un `justfile` con tareas básicas
```bash
just --edit
```
Contenido sugerido:
```makefile
update:
  sudo apt update && sudo apt upgrade -y

restart-ssh:
  sudo systemctl restart ssh
```
- 🎯 Objetivo: Automatizar comandos administrativos comunes
- 🔁 Clásico: Crear alias manuales o escribir scripts largos
- ✅ Beneficio: Sintaxis limpia, reutilizable, documentación embebida

---

### 📦 Ejercicio 2: Ejecutar tareas con `just`
```bash
just update
just restart-ssh
```
- 🎯 Objetivo: Ejecutar tareas como si fueran comandos nativos
- 🔁 Clásico: Copiar/pegar comandos cada vez
- ✅ Beneficio: Menor error humano, más productividad

---

### 🧩 Ejercicio 3: Parámetros y variables en tareas
```makefile
say NAME="mundo":
  echo "Hola {{NAME}}"
```
```bash
just say NAME=admin
```
- 🎯 Objetivo: Parametrizar tareas
- 🔁 Clásico: Bash scripts más complejos
- ✅ Beneficio: Plantillas simples, sin lógica innecesaria

---

## 👀 2. ENTR – Ejecutar comandos al detectar cambios

### 📝 Ejercicio 1: Ejecutar acción al editar archivo
```bash
echo archivo.txt | entr echo "Archivo modificado"
```
- 🎯 Objetivo: Detectar modificaciones y reaccionar automáticamente
- 🔁 Clásico: No hay equivalente directo sin `inotify`
- ✅ Beneficio: Ideal para testing, scripts en desarrollo o CI manual

---

### 🔄 Ejercicio 2: Compilar o recargar algo al guardar
```bash
ls *.sh | entr ./mi_script.sh
```
- 🎯 Objetivo: Ejecutar scripts automáticamente al editarlos
- 📌 Escenario: Desarrollo, pruebas, backups programados

---

## 📁 3. ZOXIDE – Navegación de directorios ultra rápida

### 🚶 Ejercicio 1: Acceder a directorios recientemente visitados
```bash
z /etc
z /var/log
z /etc
```
- 🎯 Objetivo: Saltar rápidamente entre ubicaciones previas
- 🔁 Clásico: `cd ../../` o recordar rutas
- ✅ Beneficio: Ahorro de tiempo, navegación por frecuencia

---

### 🧠 Ejercicio 2: Búsqueda fuzzy de rutas
```bash
zi log
```
- 🎯 Objetivo: Buscar directorios sin escribir ruta exacta
- 🔁 Clásico: `cd` + `tab` o `find`
- ✅ Beneficio: Rápido, predictivo, personalizable

---

### 📈 Ejercicio 3: Ver historial de navegación
```bash
zoxide query -l
```
- 🎯 Objetivo: Auditar rutas visitadas
- ✅ Beneficio: Transparencia y trazabilidad de uso

---

✅ Con estos ejercicios, el participante podrá mejorar notablemente su velocidad de navegación y ejecución en terminal, adoptando herramientas modernas fáciles de integrar.

Siguiente archivo 👉 `modulo3-script-automatizacion.md`
