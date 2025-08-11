# ⚙️ Módulo 2 - Prerrequisitos: Procesos y Rendimiento en Linux

Este documento describe los requisitos previos para ejecutar correctamente los comandos del **Módulo 2** del curso **Shell Evolved**, enfocado en monitoreo de recursos y análisis de rendimiento desde consola.

---

## 📦 Herramientas a instalar en este módulo

- `btm` → Monitor visual tipo `htop`, pero más moderno y detallado
- `procs` → Visualizador avanzado de procesos con colores y columnas claras
- `hyperfine` → Benchmarking para comparar velocidad entre comandos o scripts

---

## 🖥️ Entornos compatibles

| Entorno                   | Compatible | Observaciones |
|---------------------------|------------|---------------|
| Ubuntu Server 24.04 (VM) | ✅          | Recomendado   |
| Ubuntu Server 24.04 (WSL)| ⚠️ Parcial | Algunas interfaces gráficas no renderizan bien en terminal WSL clásico |
| VPS Ubuntu 24.04 LTS     | ✅          | Ideal por entorno real de producción |

> ⚠️ En WSL2, se recomienda usar una terminal compatible como **Windows Terminal** o **Alacritty** para visualizar `btm` correctamente.

---

## 🛠️ Paso 1: Actualizar sistema y preparar entorno

```bash
sudo apt update && sudo apt upgrade -y
```

---

## 📁 Paso 2: Instalar herramientas base necesarias

```bash
sudo apt install -y \
  curl \
  unzip \
  snapd \
  cargo \
  build-essential
```

> 🔧 `build-essential` es requerido por `cargo` para compilar `procs` e `hyperfine` correctamente.

---

## 📌 Paso 3: Verificar que cargo esté en el PATH

```bash
cargo --version || echo "Instala cargo con: sudo apt install cargo"
```

> Si `cargo` no está presente, se debe instalar manualmente o verificar permisos en entornos restringidos.

---

## 💡 Consejos adicionales

- Usa `tmux` o `screen` si vas a dejar herramientas como `btm` corriendo en segundo plano
- Si estás en WSL y ves errores con la renderización, prueba desde una VM o VPS real

---

✅ Con estos pasos, tu sistema queda listo para instalar las herramientas del Módulo 2

Siguiente archivo 👉 `modulo2-instalacion-comandos.md`
