# 🤖 Módulo 4 - Automatización con script de instalación

Este documento describe el uso del script `modulo4_instalar_diagnostico.sh` para instalar automáticamente las herramientas del **Módulo 4** del curso **Shell Evolved**, enfocadas en diagnóstico, búsqueda eficiente y análisis de disco.

---

## 🎯 Objetivo del script

- Instalar y verificar:
  - `dog` (cliente DNS)
  - `ripgrep` (`rg`)
  - `gdu` (uso de disco)
  - `fzf` (búsqueda fuzzy)
- Soportar instalación vía `snap`, `apt` o `cargo` según entorno disponible

---

## 📄 Contenido del script

**Ruta sugerida:** `scripts/modulo4_instalar_diagnostico.sh`

```bash
#!/bin/bash
# Script de instalación automática del Módulo 4 - Shell Evolved

set -e

# Actualizar sistema
echo "🔄 Actualizando repositorios..."
sudo apt update

# Instalar herramientas disponibles por APT
echo "📦 Instalando ripgrep y fzf desde APT..."
sudo apt install -y ripgrep fzf build-essential cargo curl

# Añadir ~/.cargo/bin al PATH si no existe
if ! echo "$PATH" | grep -q "cargo/bin"; then
  echo "🔧 Añadiendo cargo al PATH..."
  echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc
  source ~/.bashrc
fi

# Instalar dog (preferir snap, si no usar cargo)
if ! command -v dog &> /dev/null; then
  echo "🐶 Instalando dog..."
  if command -v snap &> /dev/null; then
    sudo snap install dog --beta || cargo install dog-cli
  else
    cargo install dog-cli
  fi
else
  echo "✅ dog ya está instalado."
fi

# Instalar gdu (snap o cargo)
if ! command -v gdu &> /dev/null; then
  echo "💾 Instalando gdu..."
  if command -v snap &> /dev/null; then
    sudo snap install gdu || cargo install gdu
  else
    cargo install gdu
  fi
else
  echo "✅ gdu ya está instalado."
fi

echo "✅ Módulo 4 instalado correctamente. Puedes continuar con los ejercicios."
```

---

## ⚙️ Cómo usar el script

1. Asegúrate de tener los prerrequisitos ejecutados desde `modulo4-prerrequisitos.md`

2. Asigna permisos de ejecución:
```bash
chmod +x scripts/modulo4_instalar_diagnostico.sh
```

3. Ejecuta el script:
```bash
bash scripts/modulo4_instalar_diagnostico.sh
```

---

## ✅ Validación posterior

```bash
dog --version
rg --version
gdu --version
fzf --version
```

---

Una vez finalizado, pasa a los ejercicios documentados en `modulo4-ejercicios-comparativos.md`
