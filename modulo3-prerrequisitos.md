# ⚙️ Módulo 3 - Prerrequisitos: Automatización y Productividad desde la Terminal

Este documento define los requisitos necesarios para preparar el entorno del **Módulo 3** del curso **Shell Evolved**, donde trabajaremos con herramientas que potencian la automatización y navegación eficiente desde consola.

---

## 🧰 Herramientas incluidas en este módulo

- `just` → Reemplazo moderno de `make` para tareas repetitivas
- `entr` → Ejecuta comandos cuando un archivo cambia
- `zoxide` → Navegación de directorios rápida e inteligente (mejor que `cd`)

---

## 🖥️ Entornos compatibles

| Entorno                   | Compatible | Observaciones |
|---------------------------|------------|---------------|
| Ubuntu Server 24.04 (VM) | ✅          | Ideal         |
| Ubuntu Server 24.04 (WSL)| ✅          | Requiere cargo manual |
| VPS Ubuntu 24.04         | ✅          | Recomendado si se trabaja por SSH

> ⚠️ Todas las herramientas de este módulo requieren `cargo` para su instalación si no se usan versiones empaquetadas.

---

## 🔧 Paso 1: Actualización del sistema base

```bash
sudo apt update && sudo apt upgrade -y
```

---

## 📦 Paso 2: Instalación de dependencias esenciales

```bash
sudo apt install -y \
  curl \
  cargo \
  build-essential \
  entr
```

> 🔹 `entr` se instala directamente desde `apt`
> 🔹 `just` y `zoxide` se instalan desde `cargo`

---

## 📁 Paso 3: Verificar entorno de compilación Rust (cargo)

```bash
cargo --version || echo "Instala cargo con: sudo apt install cargo"
```

> 💡 Si estás en WSL, asegúrate de tener `~/.cargo/bin` en tu `$PATH`

---

✅ Listo. Tu entorno ya está preparado para instalar las herramientas del Módulo 3.

Siguiente archivo 👉 `modulo3-instalacion-comandos.md`
