# ⚙️ Módulo 4 - Prerrequisitos: Diagnóstico, Búsqueda y Uso de Disco

Este documento contiene los requisitos previos necesarios para ejecutar el **Módulo 4** del curso **Shell Evolved**, enfocado en diagnóstico de red, búsquedas eficientes y visualización moderna del uso de disco en sistemas Linux desde TTY.

---

## 🔍 Herramientas incluidas en este módulo

- `dog` → Cliente DNS moderno y visual (mejor que `dig`)
- `ripgrep` (alias `rg`) → Búsqueda de texto ultrarrápida (mejor que `grep`)
- `gdu` → Análisis de uso de disco moderno (mejor que `du`, `ncdu`)
- `fzf` → Búsqueda interactiva fuzzy para flujos rápidos

---

## 🖥️ Entornos compatibles

| Entorno                   | Compatible | Observaciones |
|---------------------------|------------|---------------|
| Ubuntu Server 24.04 (VM) | ✅          | Ideal         |
| Ubuntu Server 24.04 (WSL)| ⚠️ Parcial | Algunos paquetes pueden requerir ajustes o instalar vía `cargo` |
| VPS Ubuntu 24.04         | ✅          | Excelente para uso en producción

> ⚠️ En WSL, `snap` puede no funcionar correctamente. Se recomienda usar `cargo` o binarios `.deb` alternativos para `gdu` y `dog`.

---

## 🔧 Paso 1: Actualizar sistema

```bash
sudo apt update && sudo apt upgrade -y
```

---

## 📦 Paso 2: Instalar dependencias base

```bash
sudo apt install -y \
  curl \
  build-essential \
  ripgrep \
  fzf \
  cargo
```

> `ripgrep` y `fzf` están disponibles en los repos oficiales. `gdu` y `dog` pueden instalarse vía Snap o `cargo` si es necesario.

---

## 💡 Tip: Validar entorno Rust (cargo)

```bash
cargo --version || echo "Instala cargo con: sudo apt install cargo"
```

---

✅ Con estos pasos tu entorno está listo para comenzar la instalación de los comandos modernos del Módulo 4.

Siguiente archivo 👉 `modulo4-instalacion-comandos.md`
