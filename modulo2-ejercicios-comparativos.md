# 🧪 Módulo 2 - Ejercicios comparativos: `btm`, `procs`, `hyperfine`

Este documento contiene ejercicios detallados para cada herramienta del **Módulo 2**. Cada ejercicio compara la herramienta moderna con su equivalente clásico en Linux, destacando beneficios reales en tareas de monitoreo y benchmarking desde consola.

> Los ejercicios están diseñados para ser ejecutados desde TTY o consola remota, en Ubuntu Server 24.04 LTS.

---

## 🔵 1. BTM (Bottom) – Monitor de sistema moderno

### 📊 Ejercicio 1: Monitorear uso de CPU, RAM y red
```bash
btm
```
- 🎯 Objetivo: Visualizar uso del sistema en tiempo real con interfaz clara
- 🔁 Clásico: `top`, `htop`
- ✅ Beneficio: Interfaz gráfica en terminal, secciones divididas, navegación con teclado
- 📌 Escenario: Diagnóstico en producción sin GUI

---

### 📁 Ejercicio 2: Filtrar procesos por consumo de memoria
```bash
btm -f mem
```
- 🎯 Objetivo: Identificar qué procesos consumen más RAM
- 🔁 Clásico: `top`, `ps aux --sort=-%mem`
- ✅ Beneficio: Orden visual dinámico, actualizaciones en vivo, mejor lectura

---

### 🧱 Ejercicio 3: Ver I/O por proceso
```bash
btm -f io
```
- 🎯 Objetivo: Ver qué procesos generan más lectura/escritura en disco
- 🔁 Clásico: No disponible fácilmente sin herramientas externas (`iotop`)
- ✅ Beneficio: Integración directa, sin instalar más paquetes

---

## 🟡 2. PROCS – Visualizador mejorado de procesos

### 📋 Ejercicio 1: Listar procesos con colores y columnas legibles
```bash
procs
```
- 🎯 Objetivo: Reemplazar `ps` con visualización moderna
- 🔁 Clásico: `ps aux`
- ✅ Beneficio: Encabezados claros, colores, orden y legibilidad

---

### 🔍 Ejercicio 2: Buscar procesos por nombre
```bash
procs nginx
```
- 🎯 Objetivo: Filtrar directamente procesos por nombre
- 🔁 Clásico: `ps aux | grep nginx`
- ✅ Beneficio: Sin necesidad de pipes o grep

---

### 📈 Ejercicio 3: Ordenar procesos por uso de memoria
```bash
procs --sort mem
```
- 🎯 Objetivo: Ver los procesos que más memoria usan
- 🔁 Clásico: `ps aux --sort=-%mem`
- ✅ Beneficio: Menos sintaxis, más visual, directo

---

## 🟣 3. HYPERFINE – Benchmark de comandos

### ⏱️ Ejercicio 1: Comparar velocidad entre `ls` y `exa`
```bash
hyperfine "ls -la" "exa -la"
```
- 🎯 Objetivo: Ver cuál de los comandos se ejecuta más rápido
- 🔁 Clásico: Medición manual con `time`
- ✅ Beneficio: Estadísticas múltiples, media, desviación, repeticiones automáticas

---

### 🧪 Ejercicio 2: Benchmark de scripts personales
```bash
hyperfine './backup1.sh' './backup2.sh'
```
- 🎯 Objetivo: Comparar dos versiones de un mismo script
- 🔁 Clásico: `time ./script.sh`
- ✅ Beneficio: Medición confiable, repetida, exportable

---

### 📊 Ejercicio 3: Medir impacto de parámetros en un comando
```bash
hyperfine "grep error syslog" "rg error syslog"
```
- 🎯 Objetivo: Medir eficiencia de herramientas modernas vs tradicionales
- 🔁 Clásico: Pruebas subjetivas sin estadísticas
- ✅ Beneficio: Elección informada basada en datos

---

✅ Con estos ejercicios, los participantes desarrollan habilidades reales de diagnóstico, control y medición de procesos desde la terminal con herramientas modernas.

Siguiente archivo 👉 `modulo2-script-automatizacion.md`
