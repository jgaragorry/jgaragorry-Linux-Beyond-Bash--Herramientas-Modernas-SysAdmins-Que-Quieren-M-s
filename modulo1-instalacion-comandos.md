# 📦 Módulo 1 - Instalación de comandos modernos: `exa`, `bat`, `dust`, `duf`

Este documento contiene el procedimiento completo para instalar cada herramienta del Módulo 1 del curso **Shell Evolved**, validado en Ubuntu Server 24.04 LTS.

---

## 📘 Tabla resumen

| Comando | Reemplaza a | Método de instalación | Compatibilidad WSL |
|--------|--------------|------------------------|--------------------|
| `eza`  | `ls`         | APT (`apt install`)    | ✅ Total           |
| `bat`  | `cat`        | APT (`apt install`)    | ✅ Total           |
| `dust` | `du`         | `cargo`                | ✅ Requiere `cargo`|
| `duf`  | `df`         | APT (`apt install`)    | ✅ Total           |

---

## 🔸 1. Instalar `exa`

```bash
sudo apt update && sudo apt install -y eza
```

### ✔️ Verificación:
```bash
exa --version
```

---

## 🔹 2. Instalar `bat`

```bash
sudo apt install -y bat
```

⚠️ **En Ubuntu, el ejecutable se instala como `batcat`. Para hacerlo accesible como `bat`:**

```bash
sudo ln -s /usr/bin/batcat /usr/local/bin/bat
```

### ✔️ Verificación:
```bash
bat --version
```

---

## 🔸 3. Instalar `dust` (requiere `cargo`)

```bash
cargo install du-dust
```

📁 Esto instalará `dust` en:
```
~/.cargo/bin/dust
```

Puedes agregarlo a tu `PATH`:
```bash
echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

### ✔️ Verificación:
```bash
dust --version
```

---

## 🔹 4. Instalar `duf`

```bash
sudo apt install -y duf
```

### ✔️ Verificación:
```bash
duf --version
```

---

## 💡 Comprobación final

```bash
exa -la
bat /etc/fstab
~/.cargo/bin/dust /var
duf
```

---

✅ Si todos los comandos funcionan correctamente, tu entorno ya está listo para realizar los ejercicios del Módulo 1.

Siguiente archivo 👉 `modulo1-ejercicios-comparativos.md`
