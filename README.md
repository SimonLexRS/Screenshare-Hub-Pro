# Screenshare Hub Pro

Software propietario de **Elitech Solutions**. Todos los derechos reservados.
Este repositorio distribuye el **instalador Linux** (binario cerrado). No incluye código fuente.

[Último release](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/latest)

## Novedades v1.3.1

- **Corregido**: la actualización automática desde `/admin` fallaba en Linux (`sudo: The "no new privileges" flag is set…`). Ya funciona de nuevo.
- **Migración importante**: las instalaciones en v1.2.0/v1.3.0 no pueden autoactualizarse; descarga el tarball v1.3.1 y ejecuta `sudo ./install.sh` **una vez** (conserva config, datos y licencia). A partir de ahí, el botón **Actualizar ahora** vuelve a funcionar.
- `update.sh` ahora rechaza tarballs con rutas inseguras antes de extraer como root.
- Novedades v1.3.0: PIN de TV obligatorio con anti-fuerza bruta, HTTP opt-in para TVs Android y corrección de pestaña + audio del sistema.

## Qué se licencia

- Puedes instalar **hubs ilimitados** (un servidor por sucursal, VLAN, etc.).
- Lo que cuenta —y se factura— es el **total de TVs/pantallas** de tu cuenta Elitech.
- Activa cada hub en `https://<IP>:8443/admin` con el email y la contraseña de [app.elitech-solutions.com](https://app.elitech-solutions.com).

## Distros

Un binario x86_64 (glibc ≥ 2.28):

- Ubuntu, Debian
- Red Hat Enterprise Linux, Rocky Linux, CentOS Stream, AlmaLinux

El instalador detecta la familia (`debian` vs `rhel`) y configura `apt`/`dnf`, `ufw`/`firewalld` y systemd.

## Descarga de archivos

Archivos del release [v1.3.1](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/tag/v1.3.1):

- [screenshare-hub-1.3.1-linux-x86_64.tar.gz](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.3.1/screenshare-hub-1.3.1-linux-x86_64.tar.gz)
- [SHA256SUMS](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.3.1/SHA256SUMS)

Con `curl`:

```bash
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.3.1/screenshare-hub-1.3.1-linux-x86_64.tar.gz
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.3.1/SHA256SUMS
sha256sum -c SHA256SUMS
```

## Instalación

```bash
tar -xzf screenshare-hub-1.3.1-linux-x86_64.tar.gz
cd screenshare-hub-1.3.1-linux-x86_64
sudo ./install.sh
```

## Actualizar

Desde `/admin` → **Sistema** → **Buscar actualizaciones** → **Actualizar ahora**, o:

```bash
sudo /opt/elitech/screenshare-hub/update.sh /ruta/screenshare-hub-1.3.1-linux-x86_64.tar.gz
```

> **Si tu instalación está en v1.2.0 o v1.3.0**: la actualización automática falla (el unit systemd
> usaba `NoNewPrivileges`, que bloquea sudo). Actualiza **una vez a mano** con el tarball v1.3.1 y
> `sudo ./install.sh`; las siguientes ya serán automáticas.

## Licencia de uso

Consulta [LICENSE](LICENSE). Queda prohibida la copia, redistribución, ingeniería inversa y elusión del licenciamiento SaaS.

Soporte y compras: [app.elitech-solutions.com](https://app.elitech-solutions.com)