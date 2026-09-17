# Screenshare Hub Pro

Software propietario de **Elitech Solutions**. Todos los derechos reservados.
Este repositorio distribuye el **instalador Linux** (binario cerrado). No incluye código fuente.

[Último release](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/latest)

## Novedades v1.4.3

- **Acceso por empresa**: si tu correo pertenece a varias empresas en Elitech, indica el identificador de la empresa al entrar al panel admin.
- **Permisos de administrador**: solo el administrador del cliente o un superadministrador puede usar el panel del Hub con su cuenta Elitech.
- **Diagnóstico integrado**: el panel muestra y permite descargar eventos recientes de acceso, licencia y servicio.
- **Acceso local de respaldo**: la contraseña admin de la instalación sigue disponible por separado.

## Qué se licencia

- Puedes instalar **hubs ilimitados** (un servidor por sucursal, VLAN, etc.).
- Lo que cuenta —y se factura— es el **total de TVs/pantallas** de tu cuenta Elitech.
- Activa cada hub en `http://<IP>/admin` con la cuenta administradora de [app.elitech-solutions.com](https://app.elitech-solutions.com); indica la empresa si el correo está en varias cuentas.

## Distros

Un binario x86_64 (glibc ≥ 2.28):

- Ubuntu, Debian
- Red Hat Enterprise Linux, Rocky Linux, CentOS Stream, AlmaLinux

El instalador detecta la familia (`debian` vs `rhel`) y configura `apt`/`dnf`, `ufw`/`firewalld` y systemd.

## Descarga de archivos

Archivos del release [v1.4.3](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/tag/v1.4.3):

- [screenshare-hub-1.4.3-linux-x86_64.tar.gz](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.3/screenshare-hub-1.4.3-linux-x86_64.tar.gz)
- [SHA256SUMS](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.3/SHA256SUMS)

Con `curl`:

```bash
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.3/screenshare-hub-1.4.3-linux-x86_64.tar.gz
curl -fL -O https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.3/SHA256SUMS
sha256sum -c SHA256SUMS
```

Con `wget`:

```bash
wget https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.3/screenshare-hub-1.4.3-linux-x86_64.tar.gz
wget https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/download/v1.4.3/SHA256SUMS
sha256sum -c SHA256SUMS
```

También puedes bajarlos desde el navegador en la [página del release](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/tag/v1.4.3).

## Instalación

Hace falta root. `install.sh` detecta Ubuntu/Debian (`apt`, `ufw`) o RHEL/Rocky/CentOS/AlmaLinux (`dnf`/`yum`, `firewalld`), instala el servicio systemd y abre los puertos.

```bash
tar -xzf screenshare-hub-1.4.3-linux-x86_64.tar.gz
cd screenshare-hub-1.4.3-linux-x86_64
sudo ./install.sh
```

Comprueba el servicio:

```bash
sudo systemctl status screenshare-hub
```

Abre `http://<IP>/admin`, inicia sesión con tu cuenta Elitech y registra las TVs.

Rutas: binario en `/opt/elitech/screenshare-hub/`, datos y licencia en `/var/lib/elitech/screenshare-hub/`, config en `/etc/elitech/screenshare-hub.env`.

## Actualizar

Desde `/admin` → **Sistema**: **Buscar actualizaciones** → **Actualizar ahora** (descarga, verifica SHA256 e instala). También puedes hacerlo a mano:

```bash
sudo /opt/elitech/screenshare-hub/update.sh /ruta/screenshare-hub-1.4.3-linux-x86_64.tar.gz
```

El instalador y `update.sh` configuran sudoers para que el servicio pueda aplicar updates sin contraseña.

> **Migración desde v1.2.0/v1.3.0**: esas versiones no pueden autoactualizarse (el unit systemd usaba
> `NoNewPrivileges`, que bloquea sudo). Actualiza **una vez a mano** descargando el tarball y ejecutando
> `sudo ./install.sh` (conserva config, datos y licencia). A partir de v1.3.1 el botón **Actualizar ahora**
> de `/admin` vuelve a funcionar.

## Desinstalar

Desde el directorio del tarball extraído:

```bash
sudo ./uninstall.sh          # conserva datos y licencia
sudo ./uninstall.sh --purge  # borra también inventario y usuario
```

## Licencia de uso

Consulta [LICENSE](LICENSE). Queda prohibida la copia, redistribución, ingeniería inversa y elusión del licenciamiento SaaS.

Soporte y compras: [app.elitech-solutions.com](https://app.elitech-solutions.com)
