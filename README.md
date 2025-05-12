# Práctica Final de Ansible

Este proyecto es la práctica final del curso de Ansible. En él se automatiza la gestión de usuarios y la configuración de un servidor web Apache en varios hosts usando Ansible.

## 📁 Estructura del proyecto

- `inventory`: archivo de inventario con los hosts `vagrant1` y `vagrant2` en el grupo `servidores`.
- `ansible.cfg`: configuración de Ansible apuntando al inventario.
- `users.yml`: playbook que crea los usuarios `carlos` y `marta` y gestiona instalación condicional de paquetes.
- `verify_user.yml`: playbook que comprueba si el usuario `carlos` existe.
- `dev_deploy.yml`: despliega Apache y configura virtual hosts.
- `get_web_content.yml`: comprueba que los servicios web funcionan correctamente.
- `site.yml`: playbook principal que importa los anteriores.
- `templates/vhost.conf.j2`: plantilla del virtual host de Apache.
- `files/index.html`: contenido web que se sirve desde los hosts.

## ▶️ Ejecución

Para ejecutar toda la automatización:

```bash
ansible-playbook -i inventory site.yml
```

Si quieres verificar usuarios sin hacer cambios reales:

```bash
ansible-playbook -i inventory verify_user.yml --check
```

## 🧰 Requisitos

- Ansible instalado en el nodo de control.
- Dos máquinas virtuales accesibles por SSH llamadas `vagrant1` y `vagrant2`.
- Claves públicas configuradas para acceso sin contraseña si es necesario.

## ✅ Objetivos alcanzados

- Gestión de usuarios y paquetes.
- Instalación y configuración de Apache con virtual hosts.
- Verificación del contenido web.
- Uso de bloques de control (`block`, `rescue`) y plantillas Jinja2.
- Separación de lógica en varios playbooks reutilizables.

---

Hecho con 💻 por [Angel Moreno](https://github.com/Angelmz501)
