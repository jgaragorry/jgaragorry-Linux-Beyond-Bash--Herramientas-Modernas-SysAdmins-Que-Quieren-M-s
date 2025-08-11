# ⚙️ Módulo 1 - Prerrequisitos: Exploradores Visuales en TTY

Este documento describe los pasos necesarios para preparar el entorno de una máquina con **Ubuntu Server 24.04 LTS** para ejecutar correctamente los comandos modernos del Módulo 1 del curso “Shell Evolved”.

---

## ✅ ¿Qué incluye este módulo?

Herramientas modernas para explorar archivos y particiones desde consola:

- `exa` → Sustituto de `ls`
- `bat` → Alternativa de `cat`
- `dust` → Sustituto visual de `du`
- `duf` → Alternativa moderna de `df`

Estas herramientas **requieren acceso sudo** para instalación y algunas dependen de `snapd` o `cargo` para su despliegue.

---

## 🖥️ Entornos compatibles

Este módulo ha sido probado en los siguientes entornos:

| Entorno                   | Compatible | Observaciones |
|---------------------------|------------|---------------|
| Ubuntu Server 24.04 (VM) | ✅          | Recomendado   |
| Ubuntu Server 24.04 (WSL)| ⚠️ Parcial | `snap` limitado; usar `cargo` |
| VPS Ubuntu 24.04 LTS     | ✅          | Sin GUI, ideal |

---

## 🛠️ Paso 1: Actualizar el sistema

```bash
sudo apt update && sudo apt upgrade -y
```

---

## 📦 Paso 2: Instalar herramientas básicas necesarias

```bash
sudo apt install -y \
  curl \
  wget \
  unzip \
  snapd \
  cargo \
  fzf \
  ripgrep \
  entr
```

> ⚠️ Si estás en WSL y `snap` no está disponible, puedes ignorarlo y usar instalación manual con `cargo` o binarios `.deb`.

---

## 🔄 Paso 3: Activar snapd (si aplica)

```bash
sudo systemctl enable snapd --now
sudo ln -s /var/lib/snapd/snap /snap
```

> Este paso puede fallar o no ser necesario en WSL.

---

## 💡 Verificación de prerequisitos

Puedes verificar que tienes todo lo necesario ejecutando:

```bash
which cargo && which snap && which curl && which wget
```

---

✅ ¡Listo! Ahora tu entorno está preparado para comenzar con la instalación de los comandos del Módulo 1.

Siguiente archivo 👉 `modulo1-instalacion-comandos.md`
