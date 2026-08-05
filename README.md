# Debian Sid + Qtile Wayland Installer

🌐 **Language:** [Español](README.es.md) | **English**

A Bash script designed to automate the migration/configuration of **Debian Sid (Unstable)** and the compilation/installation of **Qtile** with native **Wayland** support (utilizing `wlroots 0.20`).

---

## 📋 Features

- **Debian Sid Migration:** Configures the `unstable` repositories and performs a full system upgrade (`dist-upgrade`).
- **System Dependencies:** Installs all `-dev` libraries required to build Wayland and the Qtile stack.
- **Qtile & qtile-extras Installation:** Clones the official repositories and builds them with the Wayland backend enabled.
- **User Environment:** Creates XDG user directories, sets `zsh` as the default shell, and enables the SDDM display manager.
- **Display Manager Integration:** Generates the Wayland session desktop entry for SDDM (`/usr/share/wayland-sessions/qtile-wayland.desktop`).

---

## ⚠️ Important Warnings

> [!WARNING]
> **System Migration:** This script replaces APT repositories with **Debian Sid (Unstable)** and upgrades system packages. Testing this inside a virtual machine before running it on hardware is highly recommended.

> [!WARNING]
> **Python Packages (PIP):** Installation of Qtile, `qtile-extras`, and Python dependencies **does not use a virtual environment (`venv`)**. Packages are installed globally using the `--break-system-packages` flag.

---

## 🚀 Prerequisites

1. **Minimal Debian Installation:** 
   When installing Debian (via netinst or standard installer), on the software selection screen (**tasksel**):
   - **Uncheck** all desktop environments (GNOME, Plasma, XFCE, etc.).
   - **Check only:** `standard system utilities` and optionally `SSH server`.
2. A user with configured **sudo** privileges.
3. An active internet connection.

---

## 🛠️ Installation

Once booted into the TTY of your minimal Debian installation, run the following commands sequentially to install `git`, clone this repository, set permissions, and run the script:

```bash
# 1. Update package lists and install git
sudo apt update && sudo apt install -y git

# 2. Clone the repository
git clone [https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git)

# 3. Navigate into the directory
cd YOUR_REPOSITORY

# 4. Grant execution permissions to the script
chmod +x instalador.sh

# 5. Run the installation script with root privileges
sudo ./instalador.sh
