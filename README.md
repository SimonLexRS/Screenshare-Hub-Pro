# Screenshare Hub Pro

Software propietario de **Elitech Solutions**. Todos los derechos reservados.
Este repositorio distribuye el **instalador Linux** (binario cerrado). No incluye código fuente.

[Último release](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/latest)

## Novedades v1.4.1

- **Configuración de puertos desde Admin**: interfaz en `/admin` para personalizar los puertos HTTP y HTTPS, activar o desactivar HTTPS y reiniciar el hub con redirección automática.
- **Redirección automática tras actualizar**: el panel admin sondea la disponibilidad del nuevo puerto y redirige automáticamente sin error `ERR_CONNECTION_REFUSED`.
- **Compatibilidad dual de puertos**: preserva HTTPS en puerto 8443 si existen certificados previos, junto al nuevo puerto 80 HTTP.
- **Actualización fiable en Linux**: `update.sh` desacoplado vía `systemd-run` y soporte nativo para puerto privilegiado 80 en usuario `screenshare` con `CAP_NET_BIND_SERVICE`.

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

Archivos del release [v1.4.1](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/tag/v1.4.1):

- [screenshare-hub-1.4.1-linux-x86_64.tar.gz](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.1/screenshare-hub-1.4.1-linux-x86_64.tar.gz)
- [SHA256SUMS](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.1/SHA256SUMS)

Con `curl`:

```bash
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.1/screenshare-hub-1.4.1-linux-x86_64.tar.gz
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.1/SHA256SUMS
sha256sum -c SHA256SUMS
```

## Instalación

```bash
tar -xzf screenshare-hub-1.4.1-linux-x86_64.tar.gz
cd screenshare-hub-1.4.1-linux-x86_64
sudo ./install.sh
```

## Actualizar

Desde `/admin` → **Sistema** → **Buscar actualizaciones** → **Actualizar ahora**, o:

```bash
sudo /opt/elitech/screenshare-hub/update.sh /ruta/screenshare-hub-1.4.1-linux-x86_64.tar.gz
```

## Licencia de uso

Consulta [LICENSE](LICENSE). Queda prohibida la copia, redistribución, ingeniería inversa y elusión del licenciamiento SaaS.

Soporte y compras: [app.elitech-solutions.com](https://app.elitech-solutions.com)