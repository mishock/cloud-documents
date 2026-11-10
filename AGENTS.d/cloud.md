# Cloud Cursor Agent (VPS Cursor_Cloud)

- Host: 130.17.8.47 (Fornex #34-387109, имя в панели **Cursor_Cloud**; было Cursor_/Curso_)
- Роль: **резервный Cursor Agent (SSH/CLI)** для малинок и Cursor, 24/7
- Вход: `ssh cursor-cloud` (чат) / `ssh cursor-cloud-shell` (shell)
- Знания: ~/Documents (AGENTS, rules, vpn), SSH-ключи
- Google: ~/.config/google-mcp + tokens
- Веб-PWA и порты 8766/8767 **отключены** — это не сайт

- 2026-11-08T19:26:37+03:00 NetBird на cursor-cloud (Fornex 130.17.8.47): установлен v0.82.0, FQDN `cursor-cloud.netbird.cloud`, IP `100.102.143.216/16`. Management Connected. SSH/ping к Pi3 и Pi5 OK. Kali/iPhone/NAS/ПК — Connecting (хосты offline или NetBird не поднят).
- 2026-11-08T19:27:27+03:00 Пользователь: Kali пока офлайн (ожидаемо). NetBird cursor-cloud ↔ Pi3/Pi5 OK.

- 2026-11-08T19:41:28+03:00 **ЖЁСТКО:** автосинхронизация памяти ВКЛЮЧЕНА между Pi3, Pi5, Kali и cursor-cloud. Таймер `malinki-sync.timer` (~15 мин). Цель: любой агент знает, что делали остальные. Писать знания в свой `AGENTS.d/<узел>.md` (`cloud.md` на VPS), не в собранный AGENTS.md. Kali offline — подтянется при появлении в сети.
- 2026-11-08T19:43:34+03:00 тест автосинка: SYNC-CHECK-1794156214

- 2026-11-08T20:00:28+03:00 Добавлены Cursor My Machines workers для iPhone: **Документы на Pi3** (mishock/pi3-documents, worker a7a15d6f…) и **Документы на cloud** (mishock/cloud-documents, worker 97046086…). Аккаунт телефона mishock24@gmail.com. На телефоне: новый агент → репо → Self-Hosted worker.
- 2026-11-08T20:06:27+03:00 Pi5 Cursor worker short-lived: причина HTTP_PROXY:10809; фикс — только redsocks. Видны 3 worker: Pi5/Pi3/cloud.
- 2026-11-08T20:10:14+03:00 Pi5 xray: watchdog усилен — чинит pi5-vpn-tunnel :1443 (раньше не следил; из-за обрыва туннеля xray «ломался»). Tunnel keepalive 15s, RestartSec=5.

- 2026-11-08T20:15:41+03:00 VPN xray для телефона/ПК: подписки 3x-ui смотрят на мост `130.17.8.47:443`, а DNAT на Fornex был выключен (ip_forward=0, нет правил). Восстановлен сервис `vpn-bridge-dnat.service` → DNAT/MASQUERADE на `89.127.199.6:443`, UFW 443 allow + forward ACCEPT.
- 2026-11-08T20:21:18+03:00 Модель по умолчанию для Cursor (в т.ч. телефон/Agents): **Auto** (`modelId=default`). Сброшен grok-4.7 в aiSettings.modelConfig на Pi5; cli-config + CURSOR_AGENT_MODEL=auto на cloud/Pi3/Pi5.

- 2026-11-08T17:31:06+00:00 2026-11-08 Телефон xray отваливался: Vision через DNAT-мост давал FIN-WAIT-1. Фикс: dual externalProxy (direct 89.127.199.6 + bridge 130.17.8.47) в 3x-ui; мост hardened SNAT+TCPMSS+conntrack/keepalive (`vpn-bridge-dnat.sh`). На телефоне обновить подписку — брать **direct**.

- 2026-11-08T17:39:50+00:00 2026-11-08 Офис Keenetic Giga VPN (XKeen/ELTAVR_VPN): xray Mixed OK, OOM-guard на месте, туннель до 89.127.199.6 проверен (socks→exit 89.127.199.6). Клиентов на Guest сейчас нет — last_online keenetic мог быть старым без трафика.

- 2026-11-08T17:53:35+00:00 2026-11-08 VPN нестабилен на всех: причина — Vision через DNAT-мост 130.17.8.47 (сотни FIN-WAIT-1). Фикс: externalProxy только direct 89.127.199.6; subUpdates=1ч; TCP tune на сервере; conntrack моста сброшен. Мост DNAT оставлен резервом, в подписки не отдаём. Pi3/Pi5 socks 8/8 OK.

- 2026-11-08T18:17:22+00:00 Пользователь: VPS Fornex #34-387109 переименован в панели в **Cursor_Cloud** (было Cursor_/Curso_). SSH-алиас по-прежнему `cursor-cloud`, IP 130.17.8.47.

- 2026-11-09T05:28:30+00:00 VPN починен: гараж снова блокирует прямой 89.127.199.6:443. На Cursor_Cloud поднят vpn-bridge-dnat.service (DNAT 443/2096→89.127.199.6, UFW allow). Для малинок Vision через DNAT не работает — Pi3/Pi5 ходят SSH-туннелем NetBird→cloud(100.102.143.216)→89.127.199.6:443 на 127.0.0.1:1443 + xray Vision/spiderX. Pi3: pi3-vpn-tunnel.service + xray→127.0.0.1:1443. Pi5: pi5-vpn-tunnel.service на agent@100.102.143.216 (не через Pi3), docker xray-pi5 удалён (конфликт 10808), xray-nightly-update.timer disabled. Проверено exit IP 89.127.199.6 на Pi3 (10808/10809) и Pi5 (10808/10809).
- 2026-11-09T07:07:52+00:00 2026-11-09 Офис Keenetic Giga VPN починен: офисный провайдер блокирует прямой 89.127.199.6:443. XKeen outbound переведён на мост Cursor_Cloud 130.17.8.47:443 (DNAT→VPN_Server). Проверено SOCKS→exit 89.127.199.6; last_online keenetic обновлён. В routing добавлен bypass 89.127.199.6/32 и 130.17.8.47/32. OOM-guard (GOMEMLIMIT=100MiB) на месте. Guest ELTAVR_/Bridge1→REDIRECT 1181.
- 2026-11-09T07:27:31+00:00 2026-11-09 Офис Keenetic Giga VPN починен: прямой 89.127.199.6:443 с WAN офиса SYN без ответа; Vision через DNAT-мост 130.17.8.47 тоже мёртв. Решение: SSH-туннель Keenetic→Cursor_Cloud (agent@130.17.8.47) -L 127.0.0.1:1443:89.127.199.6:443 + XKeen outbound 127.0.0.1:1443 Vision. Скрипт /opt/etc/xray/keenetic-vpn-tunnel.sh, init S99vpn-tunnel, cron */2 ensure. SOCKS exit 89.127.199.6 (3/3). Ключ keenetic-vpn-tunnel в authorized_keys cloud.
- 2026-11-10T13:15:00+03:00 VPN прод на Cursor_Cloud 130.17.8.47 (3x-ui+WG). Старый VPN_Server 89.127.199.6 сервисы stop. Pi5 primary через SSH-туннель :1443→Cloud:443; Pi3 прямой. Cursor worker на Cloud жив. vpn-bridge-dnat снят. NetBird Cloud NeedsLogin.
- 2026-11-10T14:00:00+03:00 NetBird на Cursor_Cloud восстановлен: NeedsLogin → Connected, FQDN `cursor-cloud.netbird.cloud`, IP `100.102.143.216/16`. Pi3/Pi5/ПК Connected; Kali/NAS/iPhone Connecting. Канон: `netbird up --disable-dns -n cursor-cloud` (не подменять Fornex DNS — иначе при обрыве api.netbird.io не резолвится). Скрипт: `~/bin/netbird-cloud-up.sh`.
