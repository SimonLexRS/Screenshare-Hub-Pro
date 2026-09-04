# Screenshare Hub Pro

Software propietario de **Elitech Solutions**. Todos los derechos reservados.
Este repositorio distribuye el **instalador Linux** (binario cerrado). No incluye código fuente.

[Último release](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/latest)

## Novedades v1.4.2

- **Botón para presentar en pantallas no enroladas**: en la raíz `http://<IP>` se añade un botón destacado "Presione aquí para presentar" exclusivo para pantallas o navegadores aún no enrolados, facilitando el acceso directo al presentador (`/share`) para usuarios en PC.
- **Dirección limpia en pantalla**: visualización directa y destacada de la URL del servidor `http://<IP>` sin el sufijo `/tv`.
- **Guía paso a paso para el usuario**: instrucciones visuales en `/share` detallando cómo conectarse a la TV, ingresar el PIN y transmitir con audio del sistema.
- **Corrección de TVs pendientes en Admin**: solución al error en el panel admin que impedía visualizar y aprobar las pantallas pendientes.
- **Estabilidad de registro de TVs**: las sesiones de TV pendientes con conexión activa no son purgadas por el TTL del PIN.

## Qué se licencia

- Puedes instalar **hubs ilimitados** (un servidor por sucursal, VLAN, etc.).
- Lo que cuenta —y se factura— es el **total de TVs/pantallas** de tu cuenta Elitech.
- Activa cada hub en `http://<IP>/admin` con el email y la contraseña de [app.elitech-solutions.com](https://app.elitech-solutions.com).

## Distros

Un binario x86_64 (glibc ≥ 2.28):

- Ubuntu, Debian
- Red Hat Enterprise Linux, Rocky Linux, CentOS Stream, AlmaLinux

El instalador detecta la familia (`debian` vs `rhel`) y configura `apt`/`dnf`, `ufw`/`firewalld` y systemd.

## Descarga de archivos

Archivos del release [v1.4.2](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/tag/v1.4.2):

- [screenshare-hub-1.4.2-linux-x86_64.tar.gz](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.2/screenshare-hub-1.4.2-linux-x86_64.tar.gz)
- [SHA256SUMS](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.2/SHA256SUMS)

Con `curl`:

```bash
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.2/screenshare-hub-1.4.2-linux-x86_64.tar.gz
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.2/SHA256SUMS
sha256sum -c SHA256SUMS
```

## Instalación

```bash
tar -xzf screenshare-hub-1.4.2-linux-x86_64.tar.gz
cd screenshare-hub-1.4.2-linux-x86_64
sudo ./install.sh
```

## Actualizar

Desde `/admin` → **Sistema** → **Buscar actualizaciones** → **Actualizar ahora**, o:

```bash
sudo /opt/elitech/screenshare-hub/update.sh /ruta/screenshare-hub-1.4.2-linux-x86_64.tar.gz
```

## Licencia de uso

Consulta [LICENSE](LICENSE). Queda prohibida la copia, redistribución, ingeniería inversa y elusión del licenciamiento SaaS.

Soporte y compras: [app.elitech-solutions.com](https://app.elitech-solutions.com)
