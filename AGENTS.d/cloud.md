# Cloud Cursor Agent (VPS Cursor_)

- Host: 130.17.8.47 (Fornex #34-387109, имя Cursor_)
- Роль: **резервный Cursor Agent (SSH/CLI)** для малинок и Cursor, 24/7
- Вход: `ssh cursor-cloud` (чат) / `ssh cursor-cloud-shell` (shell)
- Знания: ~/Documents (AGENTS, rules, vpn), SSH-ключи
- Google: ~/.config/google-mcp + tokens
- Веб-PWA и порты 8766/8767 **отключены** — это не сайт

- 2026-11-08T19:26:37+03:00 NetBird на cursor-cloud (Fornex 130.17.8.47): установлен v0.82.0, FQDN `cursor-cloud.netbird.cloud`, IP `100.102.143.216/16`. Management Connected. SSH/ping к Pi3 и Pi5 OK. Kali/iPhone/NAS/ПК — Connecting (хосты offline или NetBird не поднят).
- 2026-11-08T19:27:27+03:00 Пользователь: Kali пока офлайн (ожидаемо). NetBird cursor-cloud ↔ Pi3/Pi5 OK.

- 2026-11-08T19:41:28+03:00 **ЖЁСТКО:** автосинхронизация памяти ВКЛЮЧЕНА между Pi3, Pi5, Kali и cursor-cloud. Таймер `malinki-sync.timer` (~15 мин). Цель: любой агент знает, что делали остальные. Писать знания в свой `AGENTS.d/<узел>.md` (`cloud.md` на VPS), не в собранный AGENTS.md. Kali offline — подтянется при появлении в сети.
- 2026-11-08T19:43:34+03:00 тест автосинка: SYNC-CHECK-1794156214
