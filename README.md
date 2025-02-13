# Despliegue de Jellyfin con Ansible

Este repositorio contiene un **playbook de Ansible** para instalar y desplegar **Jellyfin** en un servidor con **Docker**.

## 📌 Requisitos

- Un servidor con Debian/Ubuntu
- Ansible instalado en la máquina de control
- Acceso SSH al servidor

## ⚡ Instalación

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/tu_usuario/ansible-jellyfin.git
   cd ansible-jellyfin

Si te da fallo al levantar el playbook hay que instalar appArmor e hacer estos pasos:

sudo apt update
sudo apt install apparmor apparmor-utils
sudo systemctl enable apparmor
sudo systemctl start apparmor

Luego, reinicia el servicio Docker:

sudo systemctl restart docker

Esto debería permitir que Docker cargue el perfil de AppArmor sin problemas.

2️⃣ Deshabilitar AppArmor
Si no deseas usar AppArmor, puedes deshabilitarlo temporalmente para Docker:

Deshabilitar AppArmor para Docker:

sudo aa-disable /etc/apparmor.d/docker
Reiniciar Docker:

sudo systemctl restart docker

Nota: Deshabilitar AppArmor podría reducir la seguridad de tu sistema, por lo que se recomienda instalar y configurar AppArmor correctamente en lugar de deshabilitarlo.
