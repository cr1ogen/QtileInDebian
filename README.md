# Debian Sid + Qtile Wayland Installer

Script en Bash para automatizar la migración/configuración de **Debian Sid (Unstable)** y la compilación e instalación de **Qtile** con soporte nativo para **Wayland** (utilizando `wlroots 0.20`).

---

## 📋 Características

- **Migración a Debian Sid:** Configura los repositorios `unstable` y realiza la actualización general del sistema (`dist-upgrade`).
- **Dependencias del Sistema:** Instala todas las librerías `-dev` necesarias para la compilación de Wayland y la suite de Qtile.
- **Instalación de Qtile y qtile-extras:** Clona los repositorios oficiales y los compila con el backend de Wayland activado.
- **Configuración de Usuario:** Genera carpetas de usuario XDG, configura la shell predeterminada a `zsh` y habilita el servicio SDDM.
- **Integración con Display Manager:** Genera la entrada de sesión para SDDM (`/usr/share/wayland-sessions/qtile-wayland.desktop`).

---

## ⚠️ Advertencias Importantes

> [!WARNING]
> **Migración de Sistema:** Este script cambia los repositorios APT a **Debian Sid (Unstable)** y actualiza el sistema. Se recomienda probarlo previamente en una máquina virtual antes de ejecutarlo en tu entorno principal.

> [!WARNING]
> **Paquetes de Python (PIP):** La instalación de Qtile, `qtile-extras` y sus dependencias de PIP **no utiliza un entorno virtual (`venv`)**. Se realiza a nivel global del sistema utilizando la bandera `--break-system-packages`.

---

## 🚀 Requisitos Previos

1. **Instalación mínima de Debian:** 
   Al instalar Debian (desde el instalador oficial/netinst), en la pantalla de selección de programas (**Software selection / tasksel**):
   - **Desmarcar** todos los entornos de escritorio (GNOME, Plasma, XFCE, etc.).
   - **Marcar únicamente:** `standard system utilities` (*Utilidades estándar del sistema*) y opcionalmente `SSH server`.
2. Usuario con privilegios de **sudo** configurado.
3. Conexión a Internet activa.

---

## 🛠️ Instalación

Una vez dentro de la TTY de tu instalación limpia de Debian, ejecutá los siguientes comandos en orden para instalar `git`, clonar este repositorio, dar permisos al script y ejecutarlo:

```bash
# 1. Actualizar repositorios e instalar git
sudo apt update && sudo apt install -y git

# 2. Clonar el repositorio
git clone [https://github.com/TU_USUARIO/TU_REPOSITORIO.git](https://github.com/TU_USUARIO/TU_REPOSITORIO.git)

# 3. Entrar a la carpeta del proyecto
cd TU_REPOSITORIO

# 4. Otorgar permisos de ejecución al script
chmod +x instalador.sh

# 5. Ejecutar el script de instalación con privilegios de superusuario
sudo ./instalador.sh
