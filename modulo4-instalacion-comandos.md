# 📦 Módulo 4 - Instalación de comandos: `dog`, `ripgrep`, `gdu`, `fzf`

Este documento describe cómo instalar paso a paso cada una de las herramientas del **Módulo 4** del curso **Shell Evolved**, orientado al diagnóstico de red, búsquedas avanzadas y análisis visual de disco desde TTY en Ubuntu Server 24.04 LTS.

---

## 📘 Tabla resumen

| Comando    | Función                           | Método sugerido         | Compatible WSL |
|------------|------------------------------------|--------------------------|----------------|
| `dog`      | Cliente DNS moderno                | Snap o `cargo`           | ⚠️ Parcial     |
| `ripgrep`  | Búsqueda rápida (`rg`)             | APT (`apt install`)      | ✅             |
| `gdu`      | Análisis visual de uso de disco    | Snap o `cargo`           | ⚠️ Parcial     |
| `fzf`      | Búsqueda fuzzy interactiva         | APT (`apt install`)      | ✅             |

---

## 🐶 1. Instalar `dog`

### Opción 1 (si `snap` funciona):
```bash
sudo snap install dog --beta
```

### Opción 2 (alternativa con cargo):
```bash
cargo install dog-cli
```

### ✔️ Verificación:
```bash
dog google.com
```

---

## 🔍 2. Instalar `ripgrep` (`rg`)

```bash
sudo apt install -y ripgrep
```

### ✔️ Verificación:
```bash
rg --version
```

---

## 💾 3. Instalar `gdu`

### Opción 1 (snap):
```bash
sudo snap install gdu
```

### Opción 2 (cargo):
```bash
cargo install gdu
```

Agrega `cargo` al PATH si no lo hiciste antes:
```bash
echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

### ✔️ Verificación:
```bash
gdu /var
```

---

## 🔎 4. Instalar `fzf`

```bash
sudo apt install -y fzf
```

### ✔️ Verificación:
```bash
fzf --version
```

---

## ✅ Comprobación final rápida

```bash
dog --version
rg --version
gdu --version
fzf --version
```

Siguiente archivo 👉 `modulo4-ejercicios-comparativos.md`
