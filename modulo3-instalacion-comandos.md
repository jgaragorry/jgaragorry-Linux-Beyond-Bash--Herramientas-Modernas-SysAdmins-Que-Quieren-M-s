# 📦 Módulo 3 - Instalación de comandos: `just`, `entr`, `zoxide`

Este documento detalla el procedimiento completo para instalar las herramientas modernas del **Módulo 3** del curso **Shell Evolved**, centrado en automatización y navegación eficiente desde consola.

---

## 📘 Tabla resumen

| Comando   | Función                                | Método de instalación | Compatible WSL |
|----------|-----------------------------------------|------------------------|----------------|
| `just`   | Automatización de tareas (tipo `make`)  | `cargo`               | ✅             |
| `entr`   | Ejecutar comandos al cambiar archivos    | APT (`apt install`)    | ✅             |
| `zoxide` | Navegación inteligente de directorios    | `cargo`               | ✅             |

---

## 🔸 1. Instalar `just`

```bash
cargo install just
```

Agrega `cargo` al `PATH` si es necesario:
```bash
echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

### ✔️ Verificación:
```bash
just --version
```

---

## 🔹 2. Instalar `entr`

```bash
sudo apt install -y entr
```

### ✔️ Verificación:
```bash
echo test.txt | entr echo "Archivo modificado"
```

---

## 🔸 3. Instalar `zoxide`

```bash
cargo install zoxide
```

Agrega la inicialización de `zoxide` al archivo de shell:
```bash
echo 'eval "$(zoxide init bash)"' >> ~/.bashrc
source ~/.bashrc
```

### ✔️ Verificación:
```bash
zoxide --version
```

---

## 💡 Comprobación final

```bash
just --version
entr --version
zoxide --version
```

✅ Si los tres comandos están disponibles, el sistema está listo para los ejercicios del módulo 3.

Siguiente archivo 👉 `modulo3-ejercicios-comparativos.md`
