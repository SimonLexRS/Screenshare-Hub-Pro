# Screenshare Hub Pro

Software propietario de **Elitech Solutions**. Todos los derechos reservados.
Este repositorio distribuye el **instalador Linux** (binario cerrado). No incluye código fuente.

[Último release](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/latest)

## Novedades v1.1.0

- **Rebranding** en `/admin` → Marca: paletas profesionales, logo personalizado (trial y pago). Siempre visible: *Powered by Elitech Solutions*.
- **Remote Assist** (add-on): `/assist` (host) y `/assist/view` (viewer) — compartir pantalla entre usuarios.
- **Actualizaciones**: aviso en admin + descarga e instalación del release desde GitHub.

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

Archivos del release [v1.1.0](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/tag/v1.1.0):

- [screenshare-hub-1.1.0-linux-x86_64.tar.gz](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.1.0/screenshare-hub-1.1.0-linux-x86_64.tar.gz)
- [SHA256SUMS](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.1.0/SHA256SUMS)

Con `curl`:

```bash
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.1.0/screenshare-hub-1.1.0-linux-x86_64.tar.gz
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.1.0/SHA256SUMS
sha256sum -c SHA256SUMS
```

Con `wget`:

```bash
wget https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.1.0/screenshare-hub-1.1.0-linux-x86_64.tar.gz
wget https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.1.0/SHA256SUMS
sha256sum -c SHA256SUMS
```

También puedes bajarlos desde el navegador en la [página del release](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/tag/v1.1.0).

## Instalación

Hace falta root. `install.sh` detecta Ubuntu/Debian (`apt`, `ufw`) o RHEL/Rocky/CentOS/AlmaLinux (`dnf`/`yum`, `firewalld`), instala el servicio systemd y abre los puertos.

```bash
tar -xzf screenshare-hub-1.1.0-linux-x86_64.tar.gz
cd screenshare-hub-1.1.0-linux-x86_64
sudo ./install.sh
```

Comprueba el servicio:

```bash
sudo systemctl status screenshare-hub
```

Abre `https://<IP>:8443/admin`, inicia sesión con tu cuenta Elitech y registra las TVs.

Rutas: binario en `/opt/elitech/screenshare-hub/`, datos y licencia en `/var/lib/elitech/screenshare-hub/`, config en `/etc/elitech/screenshare-hub.env`.

## Actualizar desde v1.0.0

Desde `/admin` usa el banner **Descargar** → **Instalar**, o manualmente:

```bash
sudo /opt/elitech/screenshare-hub/update.sh /var/lib/elitech/screenshare-hub/updates/screenshare-hub-1.1.0-linux-x86_64.tar.gz
```

## Desinstalar

Desde el directorio del tarball extraído:

```bash
sudo ./uninstall.sh          # conserva datos y licencia
sudo ./uninstall.sh --purge  # borra también inventario y usuario
```

## Licencia de uso

Consulta [LICENSE](LICENSE). Queda prohibida la copia, redistribución, ingeniería inversa y elusión del licenciamiento SaaS.

Soporte y compras: [app.elitech-solutions.com](https://app.elitech-solutions.com)
