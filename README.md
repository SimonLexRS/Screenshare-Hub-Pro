# Screenshare Hub Pro

Software propietario de **Elitech Solutions**. Todos los derechos reservados.
Este repositorio distribuye el **instalador Linux** (binario cerrado). No incluye código fuente.

[Descargar el último release](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/latest)

## Qué se licencia

- Puedes instalar **hubs ilimitados** (un servidor por sucursal, VLAN, etc.).
- Lo que cuenta —y se factura— es el **total de TVs/pantallas** de tu cuenta Elitech.
- Activa cada hub en `https://<IP>:8443/admin` con el email y la contraseña de [app.elitech-solutions.com](https://app.elitech-solutions.com).

## Distros

Un binario x86_64 (glibc ≥ 2.28):

- Ubuntu, Debian
- Red Hat Enterprise Linux, Rocky Linux, CentOS Stream, AlmaLinux

El instalador detecta la familia (`debian` vs `rhel`) y configura `apt`/`dnf`, `ufw`/`firewalld` y systemd.

## Instalación

1. Abre [Releases](https://github.com/SimonLexRS/Screenshare-Hub-Pro/releases/latest) y descarga `screenshare-hub-1.0.0-linux-x86_64.tar.gz` y `SHA256SUMS`.
2. Verifica e instala:

```bash
sha256sum -c SHA256SUMS
tar -xzf screenshare-hub-1.0.0-linux-x86_64.tar.gz
cd screenshare-hub-1.0.0-linux-x86_64
sudo ./install.sh
```

3. Abre `https://<IP>:8443/admin`, inicia sesión con tu cuenta Elitech y registra las TVs.

## Desinstalar

Desde el directorio del tarball extraído:

```bash
sudo ./uninstall.sh          # conserva datos y licencia
sudo ./uninstall.sh --purge  # borra también inventario y usuario
```

## Licencia de uso

Consulta [LICENSE](LICENSE). Queda prohibida la copia, redistribución, ingeniería inversa y elusión del licenciamiento SaaS.

Soporte y compras: [app.elitech-solutions.com](https://app.elitech-solutions.com)
