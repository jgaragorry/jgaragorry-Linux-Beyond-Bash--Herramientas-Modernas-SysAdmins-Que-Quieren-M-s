# 🤖 Módulo 2 - Automatización con script de instalación

Este documento describe el uso del script `modulo2_instalar_procesos.sh` para instalar de manera automatizada las herramientas de monitoreo y benchmarking del **Módulo 2** del curso **Shell Evolved**: `btm`, `procs` y `hyperfine`.

---

## 🎯 Objetivo del script

- Instalar automáticamente todas las herramientas del módulo 2
- Validar la presencia de `cargo` y agregarlo al `PATH` si es necesario
- Utilizar `snap` para `btm` y `cargo` para el resto

---

## 📄 Contenido del script

**Ruta sugerida:** `scripts/modulo2_instalar_procesos.sh`

```bash
#!/bin/bash
# Script de instalación automática del Módulo 2 - Shell Evolved

set -e

echo "🔄 Actualizando paquetes..."
sudo apt update

# Requisitos básicos
sudo apt install -y snapd cargo build-essential

# Instalar btm desde snap
if ! command -v btm &> /dev/null; then
  echo "📈 Instalando btm desde snap..."
  sudo snap install btm
else
  echo "✅ btm ya está instalado."
fi

# Verificar si ~/.cargo/bin está en el PATH
if ! echo "$PATH" | grep -q "cargo/bin"; then
  echo "🛠️ Agregando ~/.cargo/bin al PATH..."
  echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc
  source ~/.bashrc
fi

# Instalar procs
if ! command -v procs &> /dev/null; then
  echo "🔍 Instalando procs..."
  cargo install procs
else
  echo "✅ procs ya está instalado."
fi

# Instalar hyperfine
if ! command -v hyperfine &> /dev/null; then
  echo "⏱️ Instalando hyperfine..."
  cargo install hyperfine
else
  echo "✅ hyperfine ya está instalado."
fi

echo "🎉 Todas las herramientas del módulo 2 han sido instaladas exitosamente."
```

---

## ⚙️ Cómo usar el script

1. Asegúrate de tener los prerrequisitos ejecutados desde `modulo2-prerrequisitos.md`

2. Asigna permisos de ejecución:
```bash
chmod +x scripts/modulo2_instalar_procesos.sh
```

3. Ejecuta el script:
```bash
bash scripts/modulo2_instalar_procesos.sh
```

---

## ✅ Validación posterior

```bash
btm
procs --version
hyperfine --version
```

---

Una vez completado este paso, continúa con los ejercicios prácticos en `modulo2-ejercicios-comparativos.md`
