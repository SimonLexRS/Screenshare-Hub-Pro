# Screenshare Hub Pro

Software propietario de **Elitech Solutions**. Todos los derechos reservados.
Este repositorio distribuye el **instalador Linux** (binario cerrado). No incluye código fuente.

[Último release](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/latest)

## Novedades v1.2.0

- **Actualizar desde admin** → Sistema: buscar releases, progreso de descarga, **Actualizar ahora**, notas y reintentos.
- Instalación automática con verificación SHA256 y reinicio del servicio (Linux).

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

Archivos del release [v1.2.0](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/tag/v1.2.0):

- [screenshare-hub-1.2.0-linux-x86_64.tar.gz](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.2.0/screenshare-hub-1.2.0-linux-x86_64.tar.gz)
- [SHA256SUMS](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.2.0/SHA256SUMS)

Con `curl`:

```bash
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.2.0/screenshare-hub-1.2.0-linux-x86_64.tar.gz
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.2.0/SHA256SUMS
sha256sum -c SHA256SUMS
```

## Instalación

```bash
tar -xzf screenshare-hub-1.2.0-linux-x86_64.tar.gz
cd screenshare-hub-1.2.0-linux-x86_64
sudo ./install.sh
```

## Actualizar

Desde `/admin` → **Sistema** → **Buscar actualizaciones** → **Actualizar ahora**, o:

```bash
sudo /opt/elitech/screenshare-hub/update.sh /ruta/screenshare-hub-1.2.0-linux-x86_64.tar.gz
```

## Licencia de uso

Consulta [LICENSE](LICENSE). Queda prohibida la copia, redistribución, ingeniería inversa y elusión del licenciamiento SaaS.

Soporte y compras: [app.elitech-solutions.com](https://app.elitech-solutions.com)
