# Screenshare Hub Pro

Software propietario de **Elitech Solutions**. Todos los derechos reservados.
Este repositorio distribuye el **instalador Linux** (binario cerrado). No incluye código fuente.

[Último release](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/latest)

## Novedades v1.4.0

- **Conexión directa a la pantalla en `http://<IP>`**: la pantalla/TV se conecta directamente en la raíz `/` sin necesidad de ingresar `/tv` ni especificar puerto en la URL.
- **HTTP en puerto 80 por defecto**: listener nativo HTTP en puerto 80 sin requerir certificados TLS autofirmados para uso en red local. HTTPS pasa a ser opcional (`ENABLE_HTTPS=true`).
- **Presentador en `/share`**: ruta dedicada para compartir pantalla y enlaces bidireccionales con la pantalla.
- **Mejora integral de audio**:
  - Supresión de duplicidad local (`suppressLocalAudioPlayback`): el audio se envía 100% a la pantalla y se silencia en la PC local para evitar eco y duplicidad.
  - Bitrate de audio a 128 kbps (estéreo de alta fidelidad 48 kHz).
  - En la pantalla (TV), intento automático de reproducción con sonido sin mutear de entrada, y desbloqueo de sonido al pulsar cualquier tecla o botón del control.
- **Monitoreo en Admin**: se oculta el codec utilizado en las métricas activas.

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

Archivos del release [v1.4.0](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/tag/v1.4.0):

- [screenshare-hub-1.4.0-linux-x86_64.tar.gz](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.0/screenshare-hub-1.4.0-linux-x86_64.tar.gz)
- [SHA256SUMS](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.0/SHA256SUMS)

Con `curl`:

```bash
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.0/screenshare-hub-1.4.0-linux-x86_64.tar.gz
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.0/SHA256SUMS
sha256sum -c SHA256SUMS
```

## Instalación

```bash
tar -xzf screenshare-hub-1.4.0-linux-x86_64.tar.gz
cd screenshare-hub-1.4.0-linux-x86_64
sudo ./install.sh
```

## Actualizar

Desde `/admin` → **Sistema** → **Buscar actualizaciones** → **Actualizar ahora**, o:

```bash
sudo /opt/elitech/screenshare-hub/update.sh /ruta/screenshare-hub-1.4.0-linux-x86_64.tar.gz
```

## Licencia de uso

Consulta [LICENSE](LICENSE). Queda prohibida la copia, redistribución, ingeniería inversa y elusión del licenciamiento SaaS.

Soporte y compras: [app.elitech-solutions.com](https://app.elitech-solutions.com)