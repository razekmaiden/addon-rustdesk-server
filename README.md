# Home Assistant Add-on: RustDesk-Server

[![GitHub Release][releases-shield]][releases]
[![License][license-shield]](LICENSE)

![Supports aarch64 Architecture][aarch64-shield]
![Supports i386 Architecture][i386-shield]

[RustDesk-Server][rustdesk-server] permite compartir archivos con otros de manera
sencilla.

[![Abre tu instancia de Home Assistant y muestra el diálogo de añadir repositorio de add-ons
con una URL específica pre-llenada.][add-repo-shield]][add-repo]
[![Abre tu instancia de Home Assistant y muestra el panel de un add-on de Supervisor.][add-addon-shield]][add-addon]

## Acerca de

Este add-on te permite auto-hospedar tu propio servidor RustDesk
en tu HomeAssistant, compatible con Raspberry Pi 4 y otras arquitecturas soportadas.

Si utilizas RustDesk, deberías tener tu propio servidor RustDesk.
Los servidores públicos de RustDesk están destinados a fines de prueba e investigación
y no están equipados para manejar grandes cantidades de tráfico.
Esto significa que el tiempo necesario para establecer una conexión
a través de los servidores públicos puede variar considerablemente y a veces incluso fallar
si el servidor está sobrecargado.
Además, si la perforación de puertos (hole punching) falla y la conexión se enruta
a través del servidor de retransmisión público... algunos días puede ser
extremadamente rápida... otros no tanto.

## Soporte

No soy desarrollador ni tengo formación en programación, soy simplemente
autodidacta.
Si tienes alguna pregunta sobre HA y sus add-ons puedes consultar:

- [El Foro comunitario francófono][hacf] de HomeAssistant
- [El Foro comunitario anglófono][forum] de HomeAssistant.
- [El servidor Discord][discord-ha] de HomeAssistant.

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
[add-repo]: https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A//github.com/casse-boubou/hassio-addons
[add-repo-shield]: https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg
[releases]: https://github.com/casse-boubou/addon-rustdesk-server/releases
[releases-shield]: https://img.shields.io/github/v/release/casse-boubou/addon-rustdesk-server
[license-shield]: https://img.shields.io/github/license/casse-boubou/addon-rustdesk-server
[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[i386-shield]: https://img.shields.io/badge/i386-yes-green.svg
[rustdesk-server]: https://github.com/rustdesk/rustdesk-server
[discord-ha]: https://discord.gg/c5DvZ4e
[forum]: https://community.home-assistant.io
[hacf]: https://forum.hacf.fr/
[Frosh]: https://github.com/casse-boubou
