# Home Assistant Add-on: RustDesk-Server

## Acerca de

Este add-on te permite auto-hospedar tu propio servidor [RustDesk][rustdesk] en tu HomeAssistant, compatible con Raspberry Pi 4 y otras arquitecturas soportadas.

Si utilizas RustDesk, deberías tener tu propio [servidor RustDesk][servidor_rustdesk]. Los servidores públicos de RustDesk están destinados a fines de prueba e investigación y no están equipados para manejar grandes cantidades de tráfico. Esto significa que el tiempo necesario para establecer una conexión a través de los servidores públicos puede variar considerablemente y a veces incluso fallar si el servidor está sobrecargado. Además, si la perforación de puertos (hole punching) falla y la conexión se enruta a través del servidor de retransmisión público, algunos días puede ser extremadamente rápida y otros no tanto.

## Instalación

Primero, añade el repositorio al store de add-ons de Home Assistant (`https://github.com/casse-boubou/hassio-addons`):

[![Abre tu instancia de Home Assistant y muestra el diálogo de añadir repositorio de add-ons
con una URL específica pre-llenada.][add-repo-shield]][add-repo]

Luego busca RustDesk-server en el store y haz clic en instalar:

[![Abre tu instancia de Home Assistant y muestra el panel de un add-on de Supervisor.][add-addon-shield]][add-addon]

## Arquitecturas Soportadas

Este add-on soporta las siguientes arquitecturas:
- **aarch64** (ARM 64-bit, Raspberry Pi 4, etc.)
- **i386** (Intel/AMD 32-bit)

## Configuración

Ejemplo de configuración del add-on:

```yaml
private_key: >-
  pmuglkSVWTD3kAw+H9i1WlWWgMFcvkCimlh5W6Ex7/JuHLWRYYIqOUTljEqo9Aea2DI9BQayTCAN89Y4dI8OIw==
public_key: bhy1kWGCKjlE5YutbPQHmtgyPQUGsklWDfPWOHSPDiM=
relay: midominio.duckdns.org
```

**Nota**: _¡Este es solo un ejemplo, no lo copies y pegues! ¡Crea el tuyo propio!_

### Opción: `private_key` (opcional)

Parte privada del par de claves. Si se define, fuerza el uso de una clave específica. Si se establece como `_`, fuerza el uso de cualquier clave.

### Opción: `public_key` (opcional)

Parte pública del par de claves. Si se define, fuerza el uso de una clave específica. Si se establece como `_`, fuerza el uso de cualquier clave.

### Opción: `relay` (opcional)

Este parámetro es la dirección IP (o nombre DNS) del servidor que ejecuta hbbr (generalmente este contenedor). El parámetro opcional `puerto` debe usarse si utilizas un puerto diferente al 21117 para hbbr. Ejemplo: `rustdesk.ejemplo.com:21117`

## Puertos de Red

| Puerto | Protocolo | Servicio | Descripción |
|--------|-----------|----------|-------------|
| 21114 | TCP | hbbs | API para usuarios Pro (requiere SSL proxy o puerto 443) |
| 21115 | TCP | hbbs | Prueba de tipo NAT y consulta de estado - **REQUERIDO** |
| 21116 | TCP | hbbs | Perforación TCP (hole punching) y servicio de conexión |
| 21116 | UDP | hbbs | Registro de ID y servicio de latido (heartbeat) - **REQUERIDO** |
| 21117 | TCP | hbbr | Servicios de retransmisión (Relay) - **REQUERIDO** |
| 21118 | TCP | hbbs | Cliente web de RustDesk (opcional) |
| 21119 | TCP | hbbr | Cliente web de RustDesk (opcional) |

> **Nota**: Si no necesitas soporte para el cliente web, los puertos 21118 y 21119 pueden desactivarse.

## Solución de Problemas

### Las claves no coinciden
Si recibes un error indicando que las claves proporcionadas y las presentes en la carpeta de configuración no son idénticas, asegúrate de proporcionar solo un conjunto de claves (ya sea a través de la configuración o en archivos).

### Falta una clave
Debes proporcionar AMBAS claves (privada y pública) o ninguna. Si no proporcionas claves, hbbs generará un par automáticamente.

### Par de claves inválido
Verifica que tus claves sean un par válido de Ed25519. Puedes generarlas usando las herramientas de RustDesk.

## Registro de Cambios y Versiones

Puedes consultar el registro de cambios en [GitHub aquí][releases].

## Soporte

No soy desarrollador ni tengo formación en programación, soy simplemente autodidacta.
Si tienes alguna pregunta sobre HA y sus add-ons puedes consultar:

- [El Foro comunitario francófono][hacf] de HomeAssistant
- [El Foro comunitario anglófono][forum] de HomeAssistant
- [El servidor Discord][discord-ha] de HomeAssistant

## Licencia

MIT License

Copyright (c) 2025 [Frosh][Frosh]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[add-addon]: https://my.home-assistant.io/redirect/supervisor_addon/?addon=c751e21a_rustdesk-server
[add-addon-shield]: https://my.home-assistant.io/badges/supervisor_addon.svg
[add-repo]: https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fcasse-boubou%2Fhassio-addons
[add-repo-shield]: https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg
[discord-ha]: https://discord.gg/c5DvZ4e
[forum]: https://community.home-assistant.io
[hacf]: https://forum.hacf.fr/
[Frosh]: https://github.com/casse-boubou
[releases]: https://github.com/casse-boubou/addon-rustdesk-server/releases
[rustdesk]: https://rustdesk.com/
[servidor_rustdesk]: https://github.com/rustdesk/rustdesk-server
