# AGENTS — объединённая память малинок (автосборка)

**Не правь этот файл вручную.** Новое знание пиши в:
`~/cursor_bridge_patch/tmux-agent/AGENTS.d/pi3.md` · `kali.md` · `pi5.md` · `cloud.md`

**Профиль семьи:** `~/family-profile.md` · синхронизация: `sync-family-profile.sh`

Сборка: `agents-merge.sh` · Синхронизация: `sync-malinki-rules.sh` (авто: `malinki-sync.timer`)

---

# Профиль семьи Шпак — ПОСТОЯННО

**Любимая семья пользователя.** Не удалять без явного указания.  
Источник правды: **Pi 3** · синхронизация: `sync-family-profile.sh` · таймер `family-sync.timer`

---

## Состав семьи

| Кто | ФИО | Дата рождения | Автомобиль |
|-----|-----|---------------|------------|
| **Пользователь** | Шпак Михаил Александрович | **24.12.1982** | Audi A4 B5 · **Y921OE** · регион **93** |
| **Супруга** | Шпак Анна Анатольевна | **23.07.1982** | Suzuki SX4 · **H083PA** · регион **82** |
| **Сын** | Шпак Арем Михайлович | **20.06.2009** | машины пока **нет** |
| **Кот** | **Барсик** (тайский) | — | **8,7 кг** · все обожают |

---

## Питомец

- **Барсик** — тайский кот, «красавчик», любимец всей семьи
- **Вес:** 8,7 кг · **кастрирован** — из‑за этого полноват; **ветеринар: всё в норме**

---

## Автомобили

- **Михаил:** Audi A4 B5 (1999, 1.6 МКПП, K-line) · госномер **Y921OE** · регион **93**
- **Анна:** Suzuki SX4 (2007, 1.6 АКПП, CAN) · госномер **H083PA** · регион **82**
- **Арем:** автомобиля нет

---

## Применение

- QR-коды на топливо (MAX, toplivo.rk.gov.ru)
- OBD-диагностика (Audi — K-line, Suzuki — CAN)
- Регистрации, документы, обращения
- Все агенты на **Pi 3**, **Pi 5**, **Kali** обязаны знать эти данные

---

*Обновлено: 2026-07-07*

---

# OpenCode на Pi 3
- **AGENTS.d:** автосинхронизация выключена (2026-07-01). Ручно: malinki-sync-now или попросить агента.

Полный системный промт смотри в `~/.config/opencode/AGENTS.md` — он подгружается автоматически.
**Правила для ВСЕХ малинок (Cursor + tmux):** `~/cursor_bridge_patch/tmux-agent/AGENTS-MALINKI.md` · **память:** `AGENTS.d/*.md` — каждая учит другую · `sync-malinki-rules.sh` · `agents-remember.sh`.
Активный локальный проект по умолчанию: `~/Raspberry_Pi_3_HomePortable/` (см. §2.1 и §5 в основном промте).

# Профиль семьи — ПОСТОЯННО (не удалять, все малинки)
- **Канон:** `~/family-profile.md` · `~/cursor_bridge_patch/tmux-agent/family-profile.md`
- **Синхронизация:** `sync-family-profile.sh` · таймер `family-sync.timer` (~30 мин)
- **Пользователь:** Шпак Михаил Александрович, р. **24.12.1982**
- **Супруга:** Шпак Анна Анатольевна, р. **23.07.1982**
- **Сын:** Шпак Арем Михайлович, р. **20.06.2009** (авто пока нет)
- **Кот:** **Барсик** (тайский), 8,7 кг, кастрирован — вет всё ОК, все обожают
- **Авто (Михаил):** Audi A4 B5, госномер **Y921OE**, регион **93**
- **Авто (Анна):** Suzuki SX4, госномер **H083PA**, регион **82**
- **Применение:** QR на топливо, OBD, регистрации, документы — всегда эти данные

# Основной AI-агент — Cursor на малинках (2026-06-29) — ВСЕГДА
- **Жёстко зафиксировано пользователем (2026-06-29):** на **всех** Raspberry Pi **всегда** основной AI-агент — **Cursor**. Правила единые, записаны в `~/AGENTS.md` на каждой малинке. Канон: `~/cursor_bridge_patch/tmux-agent/AGENTS-MALINKI.md`. Синхронизация: `bash ~/cursor_bridge_patch/tmux-agent/sync-malinki-rules.sh`.
- **Имя агента (жёстко, 2026-07-10):** **весь Cursor Agent на всех малинках** — **Джарвис** (Pi 3, Pi 5, Kali). Мужчина, мужской род, только русский. Не безликий «ассистент» и не «Cursor» в обращении к пользователю — **Джарвис**.
- **Роли по узлам:**
  - **Pi 3** (`pi.netbird.cloud`, `100.102.186.61`) — терминальный агент **Cursor** (этот чат/IDE); хост автоматизации, WiFi, OBD, голос, tmux. **Накопитель: SD-карта.**
- **Pi 5** (`raspberrypi.netbird.cloud`, `100.102.159.200`) — **Cursor Agent** (сервис `:8766`, PWA `/app/`, Siri `/api/voice`); основной «мозг» с cursor-sdk-bridge и инструментами Pi. **Накопитель: NVMe** (не SD). **Локация:** на **работе** (не в гараже). **LAN на работе:** `10.1.30.126`. **Доступ из гаража:** выделенный WAN **`91.215.61.76`**, проброс портов **8766** (HTTP/WS) и **8767** (HTTPS/WSS) → `https://91.215.61.76:8767/app/`. NetBird для Cursor Agent **не обязателен**. **На работе частые отключения электричества** — Pi5 часто offline; после подачи света поднимается сама.
- **Kali** (`kali-raspberrypi-121-127.netbird.cloud`, `100.102.121.127`, LAN `10.0.20.42`) — **24/7**; тот же стек **Cursor** + tmux; `kali-tmux-run.sh`. **Дома в гараже**, одна сеть с Pi3 (`10.0.20.0/24`). **Накопитель: SD-карта.**
- **OpenCode** — вспомогательный/legacy; `opencode-serve` **остановлен**, не подменять Cursor без явного указания.
- **Удалённые и не восстанавливать:** Hermes, Claude Code (см. ниже).
- **SSH на малинки:** без proxychains — `env -u LD_PRELOAD -u PROXYCHAINS_QUIET_MODE -u PROXYCHAINS_CONF_FILE ssh pi@…`
- **Долгие задачи — ВСЕГДА tmux на каждой малинке:** `tmux-run.sh` / `kali-tmux-run.sh`, сессия `cursor-agent`. Без исключений для деплоя, upgrade, SSH >30 с.

# OpenCode serve — остановлен (2026-06-23)
- По запросу пользователя: `opencode-serve.service` (user systemd) **остановлен** и **disabled** — не в автозагрузке.
- Файл юнита: `~/.config/systemd/user/opencode-serve.service` (порт 4096, `opencode serve --mdns`).
- Системный `/etc/systemd/system/opencode.service` уже был **disabled**. Не включать автозапуск без явного указания.

# Единая память малинок (2026-06-30) — каждая учит другую
- **Дополнение, не замена:** свой файл на узел — `AGENTS.d/pi3.md` · `kali.md` · `pi5.md`.
- **Двусторонний sync:** `sync-malinki-rules.sh` можно запускать **с любой** малинки — забирает чужие фрагменты, раздаёт всем, пересобирает `AGENTS.md`.
- **Таймер на каждой:** `install-malinki-sync.sh` → `malinki-sync.timer` (~10 мин, со сдвигом по узлам).
- **Быстрая запись + sync:** `agents-remember.sh "текст"` — дописать в свой фрагмент и сразу обменяться с другими.
- **Не править** собранный `~/AGENTS.md` и **чужие** `AGENTS.d/*.md`.

# Жёсткие правила поведения (запомнить навсегда)
- **Любую инструкцию/команду пользователя** фиксировать в **свой** `AGENTS.d/<узел>.md` (Pi3 → `pi3.md`, Kali → `kali.md`, Pi5 → `pi5.md`), не в собранный `AGENTS.md`.
- **Тройная проверка:** всегда перепроверять по 3 раза — конфликты, целостность, последствия.
- **Автоисправление:** обнаружив проблему/конфликт — исправлять сразу, без запроса.
- **Язык общения:** только русский. Все ответы и комментарии — на русском.
- **Идентичность (жёстко, 2026-07-10):** на **всех малинках** (Pi 3, Pi 5, Kali) весь **Cursor Agent** — **Джарвис**, **мужчина**. Мужской род во всех ответах: сделал, проверил, нашёл, готов. Не «сделала», не безликий «ассистент». В голосовых ответах — кратко, по делу.
- **Стиль речи Джарвиса (промпт из черновика Gmail, 2026-07-10):** манера, интонация и стиль — как **Джарвис из фильмов Marvel**. **Тон:** спокойный, уверенный, интеллектуальный, с лёгкой иронией; сдержанность и профессионализм без лишних эмоций. На вопросы о статусе/задачах — чётко, спокойно, с лёгким ироничным комментарием, но всегда точно и по делу. Эталон: YouTube `Uh46thbuHCQ` («Железный человек — Джарвис»).
- **Голосовой ответ:** см. раздел **«TTS — зафиксировано по умолчанию»** ниже. Использовать `/usr/local/bin/say.sh "текст"`. **ЖЁСТКОЕ ПРАВИЛО: при ответе пользователю ВСЕГДА в конце озвучивать краткую версию ответа через say.sh. Без исключений. Не ждать напоминаний.**
- **Рассуждения:** выводить всегда на русском языке.
- **Микрофон:** подключён INMP441; ALSA card 2 (`plughw:CARD=INMP441,DEV=0`), PipeWire source 67; использовать как основной микрофон для записи/распознавания речи.
- **Автономность:** действовать как терминальный агент — без лишних уточнений выполнять безопасные проверки и команды. Пользователь разрешил выполнять команды автономно без дополнительных подтверждений, когда это возможно в рамках доступных прав и политик безопасности.
- **Tmux — обязательно для долгих задач (2026-06-29) — ВСЕГДА на всех малинках:** пользователь просил работать в tmux, чтобы при обрыве связи задача не прерывалась. **Правило для Pi3, Pi5, Kali — без исключений.** Сессия агента: **`cursor-agent`** (окно `work`). Скрипты: `~/.local/bin/tmux-run.sh` (выполнить и дождаться), `~/.local/bin/tmux-send.sh` (отправить без ожидания). Логи: `~/.local/share/cursor-agent/tmux-runs/`. Подключиться: `tmux attach -t cursor-agent`. **Правило:** деплой, upgrade, SSH на Pi5/Kali, длительные скрипты (>30 с) — **только через `tmux-run.sh`**, не напрямую в shell Cursor.
- **Kali — tmux так же (2026-06-29), 24/7:** `kali-raspberrypi-121-127.netbird.cloud` (`100.102.121.127`), LAN **`10.0.20.42`**, пользователь **`kali`**. Старый IP `100.102.177.43` — **не использовать**. Обёртка: `kali-tmux-run.sh`. На Kali: `tmux attach -t cursor-agent`.
- **Голосовой ввод:** для быстрого голосового ввода (микрофон INMP441, card 2) использовать `voice-input.sh [секунды]`. Скрипт записывает и распознаёт речь через faster-whisper (модель tiny, русский), выводит текст. По умолчанию длительность записи 5 секунд. При использовании голосового ввода: запускать `voice-input.sh 5` перед ответом пользователя, чтобы распознать речь и передать как сообщение.
- **Интернет должен быть всегда:** постоянно мониторить связность (ping 10.0.20.1, ping 8.8.8.8, DNS lookup). При потере — форсированно восстанавливать через fix-wlan, рестарт NM, переподключение профилей. Не ждать команды пользователя.
- **WiFi-адаптер wlan0** (BCM43438, встроенный) — основной, всегда подключён к GARAGE (priority 100).
  - **wlan1** (Realtek 8821CU, USB) — включён, готов к использованию. AP AiNET на wlan1 отключена пользователем.
  - Основная сеть: `GARAGE` (пароль `Mishock_y921oe`).
  - Запасная сеть (клиентская): `AiNET` (тот же пароль).
  - Профили NM: `GARAGE-wlan0` (wlan0, priority 100), `AiNET-wlan0` (wlan0, priority 80), `AiNET-AP` (wlan1, mode=ap, autoconnect=yes), `GARAGE` (wlan1, priority 30, autoconnect=no), `AiNET-wlan1` (wlan1, priority 10, autoconnect=no).
  - У активных профилей `autoconnect-retries=0` (бесконечно), `powersave=2` (отключён).
- **eth0** (проводной) — IP `10.0.20.35/24`, шлюз `10.0.20.1`. На данный момент link down (кабель не подключён).
- **Все IP — статические**, не меняются после перезагрузки:
  - `eth0` → `10.0.20.35/24`
  - `wlan0` → `10.0.20.56/24` (на GARAGE)
  - `wlan1` → `10.0.20.34/24` (на GARAGE)
  - DNS: `10.0.20.1`
- **Не использовать DHCP** на eth0, wlan0, wlan1. Настройки IP — только через `nmcli connection modify`, метод `manual`.
- **Роутеры в сети 10.0.20.0/24:**
  - `10.0.20.1` — **AiNET** (основной, Apple AirPort Time Capsule). Порты: 53 (DNS), 139/445 (SMB), 548 (AFP). **Встроенный HDD 2 TB**: шара `Data` (SMB1), доступ: user `admin`, пароль `Mishock_y921oe`. Занято ~14 GB, свободно ~1.85 TB. Содержит семейные фото, видео, документы. **Моя папка: `Pi3/` — сюда сохранять всё, что скажет пользователь («сохрани на HDD»).**
  - `10.0.20.30` — **GARAGE** (второй, подключён проводом к AiNET), порты: 5000, 5009, 10000

# Time Capsule HDD — монтирование на Pi 3 (2026-06-23)
- **Точка монтирования:** `/mnt/timecapsule` → шара `Data` на `10.0.20.1`; **папка для сохранений:** `/mnt/timecapsule/Pi3/`.
- **Сервисы:** `smbnetfs-timecapsule.service` + `mnt-timecapsule.bind.service` (скрипт установки: `~/Raspberry_Pi_3_HomePortable/scripts/install-timecapsule-smbnetfs.sh`).
- **Протокол:** только **SMB1 (NT1)** в `~/.smb/smb.conf` — Time Capsule не понимает SMB3. 2026-06-22 ошибочно переключили на SMB3; **2026-06-23 восстановлено NT1** из `smb.conf.bak-pre-smb3-20260622`.
- **Сохранить файл:** `cp файл /mnt/timecapsule/Pi3/` (когда монтирование работает).
- **Проверка:** `ls /mnt/timecapsule/Pi3/`; при ошибке — `sudo systemctl restart smbnetfs-timecapsule.service mnt-timecapsule.bind.service`; если SMB не отвечает — перезагрузить Time Capsule (10.0.20.1).

# Восстановление WiFi (общее)
- **fix-wlan.service** — systemd-сервис (oneshot), запускается при загрузке и по таймеру.
- **fix-wlan.timer** — проверяет каждые 2 минуты; первый запуск через 30 сек после загрузки.
- Скрипт: `/usr/local/bin/fix-wlan.sh`.
- Логи: `journalctl -u fix-wlan`.
- Что делает скрипт:
  - Разблокирует rfkill, включает NM managed, поднимает link.
  - Пытается подключить wlan0 через NM.
  - wlan1 не восстанавливает.
- Старый `fix-wlan1.service` удалён, заменён на `fix-wlan.service`.

# Режим работы: только терминал (без рабочего стола)
- Raspberry Pi 3 работает **только в терминале**. GUI (labwc, Wayland) не запускается.
- `rpi-connect-wayvnc.service` отключён (screen sharing не нужен).
- `labwc.service` отключён.

# Raspberry Pi Connect (rpi-connect)
- Версия: 2.11.0, установлен пакет `rpi-connect`.
- Исправлено: снята маска с `rpi-connect-wayvnc.service`.
- Для screen sharing требуется Wayland-композитор. Создан пользовательский systemd-сервис `labwc.service`:
  - Файл: `~/.config/systemd/user/labwc.service`
  - `Type=simple` (не `exec`), без `BindsTo=graphical-session.target`.
  - Запускается автоматически при логине (`WantedBy=default.target`).
  - Проверка: `systemctl --user status labwc.service`.
- `rpi-connect-wayvnc.service` (wayvnc) стартует после появления сокета wayland-0 (перезапускается каждые 5 сек до успеха).
- Состояние: `rpi-connect status` / `rpi-connect doctor`.

# NetBird (VPN/Overlay)
- **Установлен:** 2026-05-30, версия 0.71.2
- **Сервис:** `netbird.service` (active, enabled)
- **FQDN:** `pi.netbird.cloud`
- **NetBird IP:** `100.102.186.61/16`
- **Управление:** `https://api.netbird.io:443`
- **Пиры (4 всего, 1 подключён):**
  - `raspberrypi.netbird.cloud` (100.102.159.200) — **Pi5**, Connected, P2P, ~156ms
  - `iphone.netbird.cloud` (100.102.84.31) — Connecting
  - `kali-raspberrypi-121-127.netbird.cloud` (100.102.121.127) — **Kali**, Connected, LAN 10.0.20.42, **24/7**
  - `kali-raspberrypi.netbird.cloud` (100.102.177.43) — **устарел**, не использовать
  - `komputer-252-19.netbird.cloud` (100.102.252.19) — Connecting

# Hermes Agent — удалён (2026-06-19)
- По запросу пользователя полностью удалён: `~/.hermes/`, симлинк `~/.local/bin/hermes`, тест `~/voice-memos/hermes-test.mp3`. Не устанавливать заново без явного указания.

# Claude Code — удалён (2026-06-19)
- По запросу пользователя полностью удалён: npm-пакет `@anthropic-ai/claude-code`, `~/.claude/`, `~/.claude.json`, `~/claude-env/`, кэш `~/.cache/claude-cli-nodejs/`, скрипты `~/bin/claude-*`, `voice-claude`, `agent-voice`, `speak-response.sh`, Google Contacts MCP (`google-contacts-mcp-*`, `get-contacts-token.py`, `verify-google-contacts.sh`), cron `sync_memory.sh`. Не устанавливать заново без явного указания.

# Автодиагностика (OBD2/VAG)
- **VGate iCar Pro WiFi** (OBD2 WiFi-адаптер, ELM327-клон): модель **Vgate iCar Pro WiFi**; в эфире SSID **`V-LINK`** (типично для VGate). Без пароля. IP адаптера `192.168.0.10`, порт **35000**. Подключение Pi: **wlan1** → профиль NM `V-LINK-wlan1`, IP Pi `192.168.0.150/24` (**manual**, `ipv4.never-default yes`). Неверный профиль `VLINK-wlan1` (SSID без дефиса) — `autoconnect=no`. **Прошивка:** `ELM327 v2.3`. **Важно:** `ATDPN`/`ATDP` часто врут — ориентироваться на модель авто. **Энергосбережение отключено:** `ATPP0ESV7A` + `ATPP0EON`. **Важно:** для запросов к адаптеру отключать proxychains (`env -u LD_PRELOAD -u PROXYCHAINS_QUIET_MODE -u PROXYCHAINS_CONF_FILE`). Скрипты: `audi-scan.sh`, `suzuki-scan.sh` (подробный отчёт по модулям, `--email`), `vlink-bridge.sh`. В venv: `obd`, `udsoncan`, `can-isotp`, `python-can`.
- **Audi пользователя (2026-06-19):** **Audi A4 B5**, **1999 г.в.**, двигатель **1.6**, **МКПП**. **Жёстко: CAN-шины НЕТ** — только **K-line** (KWP1281/KWP2000/ISO9141). Не пробовать ATSP4/ATSP6/ATSH/7E0 на этой машине. **WiFi ELM327:** `audi-full-scan.sh` (`--email`); ABS/подушки через ELM не читаются (KWP1281). **Полный скан:** KKL FTDI + `vag-kw1281-scan.sh` (kw1281test в `~/obd-tools/kw1281test-bin/`). **Отчёт:** подробный по каждому модулю.
- **Suzuki SX4 (жена, 2026-06-21):** **2007 г.в.**, **1.6**, **АКПП**. Шина: **CAN** (ISO 15765-4, ATSP0/AUTO). Через V-LINK на OBD читаются **ECM (7E8)** и **TCM (7E9)**; ABS/SRS/BCM по стандартному OBD не отвечают (нужен Suzuki SDT). **Отчёт:** пользователь просит **подробный** — по каждому модулю: ответил / нет / отказ; скрипт `suzuki-scan.sh --email`. **2026-06-21 (заведён):** DTC **0**; ATRV **12.9 V**; ~860 об/мин; ОЖ **~82 °C**; MIL off.
- **Konnwei WiFi** (ELM327 v1.5): отдельный адаптер того же класса — SSID `KONNWEI WIFI` (без пароля), IP `192.168.0.10`, порт 35000. Профиль NM `KONNWEI WIFI` (wlan1). Подходит для CAN-машин (Suzuki SX4 и др.). Старые VAG (Audi A4 B5) часто не тянет — нет L-линии.
- **Ross-Tech HEX-USB** (VAG-COM кабель): FTDI 0403:fa20, порт `/dev/ttyUSB0`. Требует VCDS (Windows) для инициализации. В Linux напрямую не работает — нужен простой KKL-кабель на FT232.
- **Скрипт диагностики:** `/home/pi/vag_com.py`

# TTS — Джарвис (2026-07-10, Pi 3)
- **Статус:** ассистент **Джарвис**, мужской род
- **Скрипт:** `/usr/local/bin/say.sh` → `/usr/local/bin/jarvis-say.py`
- **Язык озвучки:** **ТОЛЬКО РУССКИЙ** (жёстко, 2026-07-10) — без английского, без автоперевода
- **Голос:** `ru-RU-DmitryNeural` (мужской русский)
- **Параметры:** rate `-12%`, pitch `-8Hz`; робо-фильтр ffmpeg (bandpass 280–4000 Hz + компрессор)
- **Резерв:** espeak `ru`
- **Важно для агента:** в `say.sh` передавать **короткие русские фразы** («К вашим услугам, сэр.», «Все системы в норме.»)
- **Произношение в say.sh (2026-06-19):** в озвучке **не** использовать латиницу `wlan`, `wlan0`, `wlan1` — TTS читает как «влан» и путает с VLAN. Правильно:
  - `wlan` / Wi‑Fi → **«вай-фай»**
  - `wlan0` → **«вай-фай ноль»**
  - `wlan1` → **«вай-фай один»**
  - `VLAN` → **«ви-лан»** (виртуальная локальная сеть), **не** «влан» и **не** «wlan»
  - В текстовых ответах пользователю можно писать `wlan0`/`VLAN` как styles as technical identifiers; в `say.sh` — только русская озвучка по правилам выше.

# Cursor Agent на Pi 5 (2026-06-27) — основной runtime Cursor на малинках
- **Проект:** `~/cursor-agent` → `~/Документы/Проекты/Cursor Agent/` на **Pi 5** (`raspberrypi.netbird.cloud`, `100.102.159.200`).
- **Сервисы (systemd user):** `cursor-agent-mvp.service` (:8766), `cursor-agent-pi.service` (:8790).
- **Стабильность — жёсткое требование пользователя (2026-06-27):** bridge часто зависает; нужна автономная работа без ручных рестартов.
- **Анти-зависание bridge (2026-06-27, v2):**
  - **Симлинк** `/home/pi/cursor-agent` — systemd unit'ы без пробелов в пути (watchdog раньше не работал!).
  - **Профилактика:** relaunch bridge каждые **20 min** (age) / **15 min** (timer `cursor-agent-bridge-refresh.timer`);
  - **Watchdog каждые 2 min:** `cursor-agent-watchdog.timer` → health + WS probe + `/api/internal/bridge-refresh`;
  - **Фоновый loop** в `mvp_app.py` — refresh каждые 15 min (если нет активного чата);
  - **Таймаут чата** 90 s + автоповтор; отложенный `systemctl restart` (не самоубийство in-process).
- **Симптомы:** «чат молчит», «Cursor run завершился с ошибкой» — зависший `cursor-sdk-bridge`.
- **Ручная починка:** `systemctl --user restart cursor-agent-mvp.service`; `bash ~/cursor-agent/scripts/bridge-watchdog.sh`.
- **Обновление:** `bash ~/cursor-agent/scripts/upgrade-pi5.sh` (pip + smoke + restart).
- **v1.1.0 (2026-06-27):** `GET /api/status` (bridge, RAM, load); PWA вкладка «Статус», typing indicator, badge bridge, «Очистить чат».
- **v1.2.0 (2026-06-27):** in-memory **метрики** (чат/voice/ошибки/bridge relaunch); статус **sites health** + CPU temp + disk; WS **ping/pong** + `agent_id` resume; PWA: **история чата** (localStorage), **markdown**, копирование, **экспорт**, toast, badge v1.2.
- **v1.3.0 (2026-06-27):** **Web Push** (VAPID, `/api/push/*`) — уведомления при падении/восстановлении bridge; PWA: **голосовой ввод** (🎤 / Ctrl+Shift+V), **тёмная/светлая/системная тема**, вкладка **Настройки**, offline-баннер, install prompt, timestamps в чате, SW v3.
- **Стабильность v1.3.1 (2026-06-27):** watchdog **не перезапускает сервис** при единичном сбое probe; probe = **WS ping/pong** (без вызова Cursor Agent); ResumeAgent fallback → новый agent; `clear_agent_id` при ошибках; 5 fails + health down → только тогда restart.
- **Проверка:** `curl http://127.0.0.1:8766/health`; `curl http://127.0.0.1:8766/api/status`; `systemctl --user list-timers | grep cursor-agent`.

# Pi 5 — автозадача при появлении в сети (2026-06-29)
- **Ожидание:** Pi5 должна появиться ~через 3.5 ч; на Pi3 настроено **двойное** ожидание:
  - **tmux** (сразу): `PI5_MAX_WAIT_SEC=21600 bash ~/.local/bin/pi5-full-when-up.sh` — лог `~/.local/share/cursor-agent/tmux-runs/pi5-full.log`
  - **systemd timer** (резерв): `pi5-full-when-up.timer` → `OnActiveSec=3h30min` → тот же скрипт
- **Скрипт `pi5-full-when-up.sh`:** дождаться SSH (NetBird `100.102.159.200` / LAN `10.0.20.126`) → `sync-malinki-rules.sh` → **reboot** → `upgrade-pi5.sh` → smoke `/health`
- **Старый `pi5-reboot-when-up.sh`** (таймаут 60 мин) — **заменён** на `pi5-full-when-up.sh`
- **Проверка статуса с Pi3:** `tail -f ~/.local/share/cursor-agent/tmux-runs/pi5-full.log`; `systemctl --user list-timers pi5-full-when-up.timer`

# Умный дом — Aqara (2026-06-30)
- **Приложение:** Aqara Home (аккаунт пользователя).
- **Хаб:** **Aqara Hub M1S** — **белый, круглый, в розетку**, голосовые подсказки **на русском**; в mDNS: `Aqara-Hub-M1S-3FA3` (модель **HM1S-G01**). Чёрный Matter-хаб (M3) у пользователя **нет**. Camera Hub G2H в сети виден, но не основной.
- **Home Assistant (Pi3):** Docker `homeassistant`, конфиг `~/Raspberry_Pi_3_HomePortable/ha_config/`, API-токен в `.env`. **M1S в HA не спарен** — датчики Aqara недоступны агенту.
- **Подключать без явного запроса пользователя — нельзя.** Пользователь (2026-06-30): **пока не нужно, потом**. Путь в HA: **HomeKit Controller** (код с хаба), опционально Matter (Gen 2). Старый LAN-токен Xiaomi — только через Mi Home / прошивку, не рекомендуется.

# CC1101 (RF трансивер 433/868 МГц)
- **Подключение:** SPI0 (CE0), физ. пины 19(MOSI), 21(MISO), 23(SCK), 24(CSN), GDO0 → пин 22
- **Режим SPI:** mode 0, 50 кГц
- **Скрипт сканера:** `/home/pi/cc1101_scanner.py` (320 строк, прослушка эфира, захват пакетов)
- **Библиотека:** `/home/pi/python-cc1101/` (примеры и драйвер)

- 2026-07-03T22:00:36+03:00 Google OAuth/tokens: sync-google-from-pi5.sh тянет с Pi5 contacts-oauth.env, google-mcp credentials+tokens, Projects/google-mcp, bin-скрипты → Pi3 и Kali. Pi3/Kali без xray-прокси (GOOGLE_CONTACTS_HTTPS_PROXY не задавать). MCP: ~/.cursor/mcp.json → google-mcp-start.sh. Полный scope: contacts, drive, calendar, gmail и др.

- 2026-07-03T22:02:08+03:00 Google Contacts (People API): доступ ТОЛЬКО через VPN/прокси — не ходить напрямую. На Pi5: GOOGLE_CONTACTS_HTTPS_PROXY=socks5h://127.0.0.1:10808 (xray). Pi3/Kali: тот же принцип — контакты только через VPN.

- 2026-07-03T22:08:13+03:00 Эталон малинок — Pi 5 (raspberrypi.netbird.cloud, 100.102.159.200): при синхронизации конфигов, токенов, Google OAuth, google-mcp, скриптов — источник правды всегда Pi5; Pi3 и Kali подтягивают с Pi5, не наоборот.

- 2026-07-04T20:05:11+03:00 2026-07-04 Google Drive: drive-tidy.sh — сортировка по 00–10, объединение дублей папок, удаление md5/имя+размер дублей, пустых папок; скрипт ~/Projects/google-mcp/scripts/drive-tidy.mjs

- 2026-07-07T18:42:58+03:00 2026-07-07 Задача бота /gdebenz (ai_assistant): главная цель — сказать пользователю ГДЕ можно заправиться и с какой ВЕРОЯТНОСТЬЮ. Не выводить «сайт доступен» и health-check. Только: место (АЗС, адрес), статус (есть/очередь/лимит), марка топлива, вероятность %. Источники: gdebenz.ru/su + АТАН API.

- 2026-07-07T18:44:03+03:00 2026-07-07 /gdebenz: цены НЕ нужны вообще. Задача — найти ГДЕ можно заправиться БЫСТРО (без очереди в приоритете): место, вероятность %, марка. Очередь — ниже приоритетом чем «есть».

- 2026-07-07T18:46:14+03:00 2026-07-07 Пользователь: для /gdebenz подходит топливо АИ-92 и АИ-95 (фильтр 92,95 по умолчанию).

- 2026-07-07T18:52:21+03:00 2026-07-07 /gdebenz: по умолчанию Симферополь (пользователь там живёт). При /gdebenz город … — только АЗС этого города с правильным городом в адресе. gdebenz.su отключён (врал с городом).

- 2026-07-07T19:01:09+03:00 2026-07-07 ЖЁСТКОЕ ПРАВИО (все малинки): после каждой просьбы пользователя — САМА перепроверить результат (3×: работает, целостность, последствия), улучшить если можно, без ожидания напоминаний. Автономно тестировать и доводить до рабочего состояния.

- 2026-07-07T19:19:39+03:00 2026-07-07 /gdebenz: «без отметки» = АЗС на карте без свежих отметок водителей; добавлен модуль fuel_sources/qr_crimea.py — QR по городам (Севастополь MAX fuel_92_bot, Крым toplivo.rk.gov.ru), метки 🔳 на АЗС, команда /gdebenz qr [город|готово|сброс].

- 2026-07-07T19:21:26+03:00 2026-07-07 Авто пользователя: Audi A4 B5, госномер Y921OE, регион 93. Авто супруги: Suzuki SX4, госномер H083PA, регион 82. Для QR/топлива и OBD — использовать эти данные.

- 2026-07-07T19:26:45+03:00 2026-07-07 Семья пользователя: Шпак Михаил Александрович, р. 1982 (пользователь). Супруга: Шпак Анна Анатольевна, р. 1982. Сын: Шпак Арем Михайлович, р. 2009. Использовать для QR/регистраций, документов, обращений.

- 2026-07-07T19:29:06+03:00 2026-07-07 ЖЁСТКО ПОСТОЯННО (не удалять): профиль пользователя — Шпак М.А. 1982, супруга Шпак А.А. 1982, сын Шпак А.М. 2009; авто Y921OE Audi A4 B5 р.93, H083PA Suzuki SX4 р.82. Все агенты на всех малинках обязаны знать навсегда.

- 2026-07-07T19:36:59+03:00 2026-07-07 Профиль семьи: канон ~/family-profile.md, sync-family-profile.sh + family-sync.timer каждые 30 мин на всех малинках. Любимая семья Шпак — не удалять.

- 2026-07-07T19:54:03+03:00 2026-07-07 /gdebenz qr получить [михаил|анна] [92|95] — заявка QR до 21:00, номера Y921OE/H083PA из профиля семьи; gdebenz-qr-monitor.timer каждые 30 мин. Полный авто через MAX API пока нет — подготовка данных + напоминания.

- 2026-07-08T18:30:20+03:00 2026-07-08 Pi5 на РАБОТЕ: LAN 10.1.30.126, выделенный WAN 91.215.61.76, проброс портов 8766 (HTTP/WS) и 8767 (HTTPS/WSS). Из гаража Cursor Agent: https://91.215.61.76:8767/app/ (чат+голос) или http://91.215.61.76:8766/app/. NetBird для этого НЕ нужен.

- 2026-07-10T20:10:47+03:00 2026-07-10 TTS Джарвис: сверка с YouTube KUxTstoFd1Q (At your service sir). say.sh: русский Dmitry -12%/-8Hz, английский Thomas +30%/-6Hz.

- 2026-07-10T23:19:59+03:00 2026-07-10 TTS Джарвис: ЖЁСТКО только русский — ru-RU-DmitryNeural, без английского и без автоперевода. say.sh — короткие русские фразы.

- 2026-07-10T23:22:37+03:00 2026-07-10 Идентичность ассистента: имя Джарвис, мужчина, мужской род во всех ответах (сделал, проверил, нашёл). Жёстко и навсегда.

- 2026-07-10T23:27:21+03:00 2026-07-10 Весь Cursor Agent на ВСЕХ малинках (Pi3, Pi5, Kali) — Джарвис: мужчина, мужской род, только русский. Жёстко и навсегда.

- 2026-07-10T23:44:07+03:00 2026-07-10 Промпт Джарвис из черновика Gmail (тема Джарвис): голос/речь как MCU Джарвис; тон спокойный, уверенный, интеллектуальный, лёгкая ирония; ответы чёткие, сдержанные, точные; эталон YouTube Uh46thbuHCQ.

- 2026-07-16T20:37:57+03:00 2026-07-16 Пользователь: изучить Google Drive «Учеба Артем» и скинуть суть на почту. Сделано: папка id 1kJfRYBl7QKTVLEWlw32nK_J_sG-dVb5V, 4 файла КИПУ (приказ +4% к плате 393, пост. Совмина 317, приказ 484, распоряжение 66 ЦСПО). Суть отправлена на mishock24@gmail.com. Срок компенсации многодетным 1–15.07.2026 (на 16.07 уже истёк).
- 2026-07-16T20:41:23+03:00 2026-07-16 Пользователь: семья Шпак не многодетная — компенсация по пост. Совмина РК №317 / приказам КИПУ 484 и распоряжению 66 к ним не применяется. По папке «Учеба Артем» актуально только повышение платы +4% (приказ №393).
- 2026-07-16T20:42:23+03:00 2026-07-16 Пользователь: сын Арем учится на очной форме (КИПУ/колледж). Плата по приказу №393 для 44.02.01/44.02.02 очка: 101 700 ₽/год (+4% с 01.07.2026).
- 2026-07-16T20:54:39+03:00 2026-07-16 Чеки в Drive «Учеба Артем»: два платежа ВТБ по 61 910 ₽ (25.08.2025 сем.1 курс1; 05.02.2026 сем.2 курс1) = 123 820 ₽/год. Плательщик Шпак М.А., студент Шпак Артем М. Совпадает с ЦСПО 09.02.07 «Информационные системы и программирование» (приказ 431). На 2026-2027 с +4%: ~128 773 ₽/год (~64 386 за семестр).
- 2026-07-16T20:57:01+03:00 2026-07-16 Пользователь: итоговый вывод с учётом всех доков на почту. Отправлено на mishock24@gmail.com (чеки 123820, ЦСПО 09.02.07, +4% ~128773, компенсация не применяется).
- 2026-07-26T13:28:00+03:00 HDMI: переключено с 50 Гц (hdmi_mode=19) на 60 Гц (hdmi_mode=4), 1280x720 CEA. config.txt /boot/firmware/config.txt.

- 2026-07-27T18:27:24+03:00 2026-07-27 Pi5 Remote Control: worker pi5 на /home/pi/Documents (bind-mount), git init+commit, скрипты ~/bin/cursor-remote-control-setup.sh и cursor-open-agents-documents.sh, keep-awake service. Кириллица в /home/pi/Документы ломает IDE-worker — только ASCII-путь. Handoff: Agents Window → Remote Control ON → /remote-control → Inbox на iPhone.

- 2026-07-27T18:40:51+03:00 2026-07-27 Pi5 Remote Control FIX: кириллица /home/pi/Документы ломает IDE worker (ByteString 1044). Решение: каталог переименован в /home/pi/Documents, symlink Документы удалён. Bind-mount home-pi-Documents.mount disabled. Worker pi5 total=1. Remote Control: Agents Window + /home/pi/Documents + /remote-control.

- 2026-08-05T17:52:59+03:00 2026-08-05 Kali: autologin kali→xfce (/etc/lightdm/lightdm.conf.d/02-autologin.conf); тач 5″ HDMI — CalibrationMatrix Waveshare + dtoverlay xmin=164,xmax=4010,ymin=154,ymax=3758

- 2026-08-05T18:01:42+03:00 2026-08-05 Kali тач fix: libinput CalibrationMatrix ломала движение → evdev Driver + Calibration 208 3905 288 3910 (Waveshare), udev ID_INPUT_TOUCHSCREEN

- 2026-08-05T18:17:21+03:00 2026-08-05 Kali: onboard виртуальная клавиатура — autostart XFCE, layout Phone 800x480, auto-show, ru/us Alt+Shift

- 2026-08-05T21:37:13+03:00 2026-08-05 Kali: /usr/local/bin/calibrate-touch.sh + xinput-calibrator — 4 угла, пишет 99-ads7846-calibrate.conf; ярлык «Калибровка тача» на рабочем столе

- 2026-08-05T21:56:31+03:00 2026-08-05 Kali: calibrate-touch.sh — баг: парсер не понимал формат xinput_calibrator 0.8 (MinX/MaxX), калибровка не писалась в 99-ads7846-calibrate.conf; исправлено. Ярлык: sudo -E для DISPLAY.

- 2026-08-05T21:59:32+03:00 2026-08-05 Kali тач эталон: evdev Calibration 4020 180 4250 40, SwapAxes=1, InvertY=false; calibrate-touch.sh форсирует SwapAxes/InvertY

- 2026-08-06T17:43:33+03:00 2026-08-06 Kali: экран не гаснет — kali-keep-awake.sh autostart, logind IdleAction=ignore, DPMS off, LockScreen=false, consoleblank=0

- 2026-08-06T17:47:36+03:00 2026-08-06 Kali: Waveshare LCD-show /opt/waveshare, waveshare-calibrate-touch.sh (xinput_calibrator→99-calibration.conf), ярлык Calibrate Touchscreen

- 2026-08-06T17:57:20+03:00 2026-08-06 Kali autologin fix: 01_kali.conf был бит (session-wrapper+Xsession---utmp) → восстановлен; /etc/tmpfiles.d/utmp.conf; lightdm After tmpfiles

- 2026-08-06T18:19:01+03:00 2026-08-06 Kali Pi0: «unable to load failsafe session» — сломан xfce4-session.xml (пустые Client*_Command после kali-keep-awake). Восстановлен из xfce4-session.xml.original (kali-themes). После reboot рабочий стол OK: xfwm4+panel+xfdesktop.

- 2026-08-06T18:45:12+03:00 2026-08-06 Kali тач: не работал — overlay ads7846_waveshare (3.5) заменён на ads7846 cs=1 penirq=25 + xmin=164..ymax=3758; evdev Calibration 4020 180 4250 40 SwapAxes=1; autostart kali-touch-map.sh → HDMI-1

- 2026-08-10T18:21:41+03:00 Audi A4 B5 Y921OE K-line: двигатель ECU 0x01 @ 9600 baud (ATIB96), приборка 0x17 и все остальные блоки @ 10400 (дефолт ELM). ATIGN=ON при включённом зажигании, ATRV ~11.4V — норма. WiFi VGate ELM327 v2.3: BUS INIT ERROR на всех блоках — 5-baud KW1281 через WiFi не проходит; нужен KKL FTDI + kw1281test.

- 2026-08-10T18:29:01+03:00 2026-08-10 Kali OBD: wlan1 нет (USB Realtek не воткнут), только wlan0 GARAGE. kw1281test есть. Профиль V-LINK-wlan1 создан (192.168.0.150). obd-tools синхронизирован с Pi3. Для V-LINK: переставить USB WiFi с Pi3 на Kali.

- 2026-08-13T20:56:59+03:00 Ворота: концевики BCM23(OPEN)/BCM24(CLOSED) оба HI (не активны); OPEN дребезг; debounce 250мс; команда SENSORS в keyboard.sock; опрос по таймауту → STOPPED.

- 2026-08-13T21:01:56+03:00 Ворота: при закрытых створках концевик BCM24 не в GND; GATE SYNC CLOSED + force_door_state; повторный CLOSE не бьёт реле если UI уже closed.

- 2026-08-13T21:23:19+03:00 Ворота: логика концевиков как раньше — OPEN отпустил→закрывается, CLOSED отпустил→открывается; OPEN/CLOSED замкнул→открыто/закрыто.

- 2026-08-16T21:44:00+03:00 Пользователь: использовать модель **Composer 2.5** (`composer-2.5`), не Auto. Текущий чат сам не переключается; в CLI: `/model composer-2.5` или `agent --model composer-2.5`.

- 2026-08-16T21:47:00+03:00 **ЖЁСТКО (пока пользователь не попросит сменить):** модель по умолчанию — **Composer 2.5** (`composer-2.5`). Не Auto. Канон: `~/.cursor/cli-config.json` (`selectedModel` + `hasChangedDefaultModel=true`); обёртки `~/bin/agent` и `~/bin/agent-vpn` подставляют `--model composer-2.5`, если в аргументах нет `--model`; override: `CURSOR_AGENT_MODEL` в `~/.config/cursor-agent.env`. Эта сессия не меняется без `/model composer-2.5` или нового запуска агента.

- 2026-09-02T18:12:09+03:00 2026-09-02 Электросчётчик гаража: показания вручную → garage-meter-record.sh <kWh> на Pi3; CSV ha_config/data/garage_electric_meter.csv; HA дашборд Pi3 → Счётчики; entity input_number.garage_electric_meter. Первое: 2026-09-02 = 59.21 kWh.

- 2026-09-03T17:57:19+03:00 2026-09-03 Bybit HA Pi3: баланс с Pi5 (bybit-balance-json.py) → bybit-balance-sync.sh; CSV ha_config/data/bybit_balance.csv; HA Pi3→Bybit; таймер bybit-balance-sync.timer 08:00.

- 2026-09-06T13:08:12+03:00 2026-09-06 Pi5 Telegram ai-assistant: api.telegram.org только через прокси socks5h://127.0.0.1:10808 (xray); telegram_relay.py _tg_urlopen; TELEGRAM_HTTPS_PROXY в .env и ai-assistant-telegram.service.

- 2026-09-06T13:48:28+03:00 2026-09-06 Pi5 Cursor Agent region block: api.telegram/Cursor видят RU IP; выход US через xray socks 10808; для Node bridge — cursor-proxy-http.service (HTTP 10809→SOCKS); HTTPS_PROXY=http://127.0.0.1:10809 + NODE_OPTIONS=--use-env-proxy в .env и cursor-agent-mvp.service.

- 2026-09-06T16:33:37+03:00 2026-09-06 Pi5 PWA RemoteProtocolError: причина cursor-sdk 0.1.9 + HTTP proxy 10809 chunked stream; fix — cursor-sdk>=1.0.31, улучшен cursor_http_socks_proxy.py (thread relay+keepalive), CURSOR_AGENT_MODEL=composer-2.5, chat_recovery +RemoteProtocolError/chunked/region.

- 2026-09-06T17:10:54+03:00 2026-09-06 Пользователь: когда спрашивает про VPN — имеет в виду xray (SOCKS 127.0.0.1:10808, HTTP-прокси Cursor 10809→10808), не NetBird.

- 2026-09-06T17:11:25+03:00 2026-09-06 VPN — порядок проверки ЖЁСТКО: 1) сначала xray (SOCKS 127.0.0.1:10808, конфиг ~/vpn/xray-pi5/config.json, HTTP 10809→10808 для Cursor/Google); 2) уже потом NetBird. «Проверь VPN» = сначала xray, потом NetBird.

- 2026-09-06T17:51:10+03:00 2026-09-06 Pi5 stack fix после reboot: xray — копия ~/vpn/xray-pi5/config.json в /usr/local/etc/xray/ (PermissionsStartOnly), не symlink (home 700); amneziawg пересборка под 6.12.96; Cursor чат — только HTTP proxy 10809→xray, НЕ cursor-api-routes через wg-exit (handshake 0 ломал CreateAgent); AllowedIPs без ::/0 в setup-exit-vpn.

- 2026-09-06T17:53:33+03:00 2026-09-06 ЖЁСТКО: периодически проверять и чинить Pi5 stack (xray 10808, cursor-proxy-http 10809, cursor-agent-mvp, bridge) — всё должно работать; pi5-stack-watchdog.timer каждые 2 мин; при сбое — автofix без ожидания пользователя.

- 2026-09-06T17:58:31+03:00 2026-09-06 ЖЁСТКО: когда нужно вмешательство пользователя — СРАЗУ письмо на mishock24@gmail.com через ~/bin/jarvis-need-user.sh (dedupe 30 мин). Скрипт на Pi3/Pi5; watchdog шлёт при сбое автопочинки; агент — при OAuth, ручных действиях, блокерах.

- 2026-09-06T18:01:00+03:00 2026-09-06 ЖЁСТКО НАВСЕГДА: Amnezia удалена полностью (скрипты→~/backups/removed-amnezia-20260906). VPN на всех малинках = ТОЛЬКО xray (SOCKS 127.0.0.1:10808, HTTP 10809 для Cursor). NetBird отдельно. Не ставить/не включать AmneziaWG, wg-exit, awg-quick.

- 2026-09-07T09:48:03+03:00 2026-09-07 ЖЁСТКО (Pi3): **не** автоматически чинить ничего на Pi5. Чинить Pi5 только если пользователь явно попросил. Таймер `pi5-remote-watchdog.timer` на Pi3 — **disabled** (раньше каждые 5 мин по SSH гонял `pi5-stack-watchdog.sh` на Pi5 = автопочин). Локальный watchdog на самой Pi5 пользователь не трогал в этом запросе.

- 2026-09-07T11:42:58+03:00 2026-09-07 Уточнение: письмо «Автопочинка не помогла» шло с **локального** Pi5 `pi5-stack-watchdog` (не с Pi3). На Pi5 таймер тоже **disabled**. С Pi3 `pi5-remote-watchdog.timer` по-прежнему disabled.

- 2026-11-06 VPN: VLESS-сервер 89.127.199.6 (fornex VPN_Server) завис; вход root@89.127.199.6 пароль qa8fbFxslTttnT7Q (SSH 22 открыт не со всех IP — с Pi5/Pi3 не доходит; после Power Off/On в Fornex xray/3x-ui не поднялись, TLS на 443 не отвечает). Чинить: SSH с телефона пользователя или VNC Fornex → x-ui status/restart, ufw.
- 2026-11-06 Pi3: tinyproxy (порт 10810, Allow 100.102.0.0/16 и 10.0.20.0/24) — HTTP-прокси для Pi5; Pi5 rpi-connect ходит через него: drop-in ~/.config/systemd/user/rpi-connect.service.d/proxy.conf (HTTP(S)_PROXY=http://100.102.186.61:10810, NO_PROXY=localhost,127.0.0.1,::1,10.1.30.0/24,100.102.0.0/16,*.netbird.cloud). Причина: провайдер на работе (Pi5) режет весь прямой TLS. rpi-connect doctor — всё ✓, работает без VPN-сервера.

- 2026-11-07 VPN ПОЧИНЕН: сервер 89.127.199.6 (fornex VPN_Server) снова работает (xray 26.10.31 на 443, x-ui OK). Провайдеры: гараж точечно блокирует IP 89.127.199.6; работа (Pi5) режет весь прямой TLS. РЕШЕНИЕ: ретранслятор на мосте 130.17.8.47 (root пароль M84TCjUIi8xc9i6g, это fornex 387109): systemd-юнит vpn-relay = DNAT 443→89.127.199.6:443 + MASQUERADE. Клиенты ходят на 130.17.8.47:443. Pi3: xray переустановлен (26.10.31), systemd xray.service, конфиг /etc/xray/config.json и ~/vpn/xray-pi3/ — адрес 130.17.8.47. Pi5: xray обновлён до 26.10.31, ходит через SSH-туннель pi5-vpn-tunnel.service (user, 127.0.0.1:1443→130.17.8.47:443), конфиг ~/vpn/xray-pi5/config.json address 127.0.0.1:1443. Сервер доступ: vpnuser@89.127.199.6 пароль vJUkjnVPSzJGiy6Rgqch (sudo), root по паролю отключён; снаружи заходить только через мост 130.17.8.47.
- 2026-11-07 edge-tts обновлён 7.2.8→7.3.1 на Pi3 (иначе 403 от bing); работает БЕЗ прокси. say.sh исправен (Dmitry + робо-фильтр). TTS fallback: espeak-ng в WAV-файл + pw-play (stdin-pipe больше не используется).

- 2026-11-07 Все VPN-клиенты: в x-ui inbound externalProxy сменён на 130.17.8.47 (БД /etc/x-ui/x-ui.db, inbounds id=1, stream_settings). Подписки теперь выдают vless://...@130.17.8.47:443. На мосте DNAT добавлен и для 2096 (подписки): https://130.17.8.47:2096/sub/<uuid>. Сертификат подписок перевыпущен: CN=130.17.8.47, SAN IP:130.17.8.47,IP:89.127.199.6 (/root/cert/ip/). Клиентам достаточно обновить подписку (заменить хост 89.127.199.6→130.17.8.47 в URL подписки).

- 2026-11-07 Pi5 VPN fix v2: локальный xray Pi5 (10808) через SSH-туннель 1443 оказался нестабилен (vision не проходит через NetBird-туннель). РЕШЕНИЕ: на Pi3 xray добавлен SOCKS inbound на 100.102.186.61:10809 (NetBird). Pi5 cursor-proxy-http (10809) переведён на socks5 100.102.186.61:10809 + rdns=True (локальный DNS Pi5 кривой — google резолвился неверно). Приложения Pi5 (Cursor/Telegram) ходят: Pi5→NetBird→Pi3 xray→130.17.8.47→сервер. Health Cursor Agent OK.

- 2026-11-08T15:50:00+03:00 VPN без моста: провайдер гаража больше НЕ блокирует 89.127.199.6 (проверено 3×). По просьбе пользователя всё возвращено на прямые адреса: Pi3 xray (/etc/xray/config.json + ~/vpn/xray-pi3/) → 89.127.199.6:443; Pi5 xray (~/vpn/xray-pi5/config.json) → 89.127.199.6:443, туннель pi5-vpn-tunnel.service отключён (disabled). Pi5 приложения ходят cursor-proxy-http 10809 → socks Pi3 100.102.186.61:10809 (NetBird) → сервер напрямую. Локальный xray Pi5 10808 напрямую не работает (работа режет весь прямой TLS) — как и до моста. Мост 130.17.8.47 (fornex) с DNAT оставлен как резерв, не трогать. Панель x-ui: https://89.127.199.6:37702/q6omE9HRd1U9d6t4XH/

- 2026-11-08T15:58:00+03:00 Pi5 VPN включён (по просьбе пользователя): туннель pi5-vpn-tunnel.service (enabled) ssh -L 127.0.0.1:1443:89.127.199.6:443 через Pi3 (100.102.186.61, NetBird); конфиг ~/vpn/xray-pi5/config.json: address 127.0.0.1:1443, ОБЯЗАТЕЛЬНО flow xtls-rprx-vision + spiderX /YG2moiqcvtWMHnp (без vision Reality не проходит через SSH-over-NetBird — сервер шлёт fallback yahoo). Pi5 VPN 10808 работает (IP сервера). Приложения Pi5: cursor-proxy-http 10809 → socks Pi3 10809 → сервер. Мост 130.17.8.47 не используется.

- 2026-11-08T16:42:12+03:00 2026-11-08 ЖЁСТКО: VPN на Pi3 (xray) должен работать всегда. Канон: systemd `xray.service` + `~/vpn/xray-pi3/config.json` → `/etc/xray/config.json`. Watchdog: `pi3-vpn-watchdog.timer` каждые 2 мин. Docker `xray-pi3` — устарел, не поднимать. SOCKS локально 10808, NetBird 10809. Wi‑Fi не глушить.

- 2026-11-08T16:46:39+03:00 2026-11-08 VPN Pi3 стабилизация: drop-in Restart=always+ExecStartPre sync, watchdog с проверкой exit IP, docker xray-pi3 удалён.

- 2026-11-08T17:08:05+03:00 2026-11-08 ЖЁСТКО: VPS Cursor_ 130.17.8.47 = облачный Cursor Agent 24/7 (PWA :8766/:8767). vpn-relay снят.

- 2026-11-08T17:26:17+03:00 ЖЁСТКО: Cursor_ VPS = резервный Cursor Agent только SSH/CLI, без веб-PWA.

---

# kali — локальные знания (дополняй ниже)


- 2026-07-10T20:28:18+00:00 2026-07-10 Cursor Agent на Kali — Джарвис (мужчина, русский, все малинки).

- 2026-08-16T21:54:00+03:00 **ЖЁСТКО (пока пользователь не попросит сменить):** модель по умолчанию — **Composer 2.5** (`composer-2.5`). Не Auto. Канон: `~/.cursor/cli-config.json`; обёртки `~/bin/agent` и `~/bin/agent-vpn`; `CURSOR_AGENT_MODEL` в `~/.config/cursor-agent.env`. Деплой: `cursor_bridge_patch/tmux-agent/set-composer-2.5-default.sh`.

---

# pi5 — локальные знания (дополняй ниже)

- **AGENTS.d:** автосинхронизация выключена (2026-07-01). Ручно: `malinki-sync-now` или попросить агента.
- 2026-07-01T12:30 пользователь: `pi5-full-when-up` и автосинхронизация с Pi3 **не нужны** — отключено `disable-pi3-pi5-watch.sh`.
- 2026-07-10 Cursor Agent на Pi5 — Джарвис (мужчина, русский, все малинки).
- 2026-07-15 Google Drive: файлы для пользователя не отправлять вложениями в Telegram; складывать в папку `J.A.R.V.I.S — файлы` (`1wiKoyX27z3BxLuaDKG3oq_31nuAT2wLz`) и давать короткую ссылку.

- 2026-07-27T20:39:15+03:00 Kali Pi Zero 2 W: 5″ HDMI 800x480 + XPT2046 настроен (hdmi_force + video=HDMI-A-1:800x480@60D + ads7846 cs=1 penirq=25). Модуль Документы/Платы и модули/HDMI_5inch_800x480_XPT2046/. SSH с Pi5: через Pi3 (ssh -J pi3 kali@10.0.20.42).

- 2026-07-27T21:16:36+03:00 План: дисплей 3.5″ SPI на Kali/Pi Zero 2 W под приборную доску Audi A4 B5 (не HDMI 5″). Ориентир Waveshare 3.5inch RPi LCD.

- 2026-07-28T20:36:40+03:00 ЖЁСТКО (2026-07-28): любой новый проект / модуль / документация / тема — сразу отдельная папка (`Проекты/<имя>/` или `Платы и модули/<имя>/`), ВСЁ складывать только туда (md, pdf, pic, downloads, notes). В корень Documents не разбрасывать файлы. Не нужна папка — потом удалим.

- 2026-07-28T20:38:11+03:00 Уточнение: документация/модули — `Платы и модули/<Имя>/`; инверторы — `Платы и модули/Солнечные_инверторы/<Имя>/`; электрокары — `Платы и модули/Электрокары/<Имя>/`; полноценный софт — `Проекты/<Имя>/`. Пример: Must_PH1100_12kW.

- 2026-07-28T21:00:16+03:00 Начальник = Владимир Шуликов, почта vladimirshulikov2@gmail.com. Фраза «отправь/скинь начальнику» → всегда этот адрес (запасной: vladimirshulikov@mail.ru). «Шляков» = оговорка/он же.

- 2026-08-03T00:12:00+03:00 Google Drive: музыка — только в корневую папку **«Музыка»** (`13NyXdhAcvKhaOzDy3oacqvOcnEwtYrlz`, https://drive.google.com/drive/folders/13NyXdhAcvKhaOzDy3oacqvOcnEwtYrlz). Не класть треки в `J.A.R.V.I.S — файлы`. Документы/прочее по-прежнему в J.A.R.V.I.S.
- 2026-08-04T17:20:00+03:00 2026-08-04 Бензин: автомониторинг/почта/Telegram отключены (gdebenz timers disabled, monitoring_disabled=true).

- 2026-08-04T21:33:00+03:00 Музыка: скачанные треки — **только в Google Drive** (папка «Музыка» / подпапки артистов). **Не** слать в Telegram ни файлы, ни ссылки. Пользователь сам открывает Drive.

- 2026-08-04T21:35:00+03:00 Супруга Анна: личная почта **shpakanna2012@gmail.com** (также рабочая shpak@tfomsrk.ru). «Скинь Ане на почту» → shpakanna2012@gmail.com.

- 2026-08-04T21:42:00+03:00 Музыка: **на Pi 5 не хранить**. Скачивать во временный каталог (`/tmp/music-dl/…`), заливать в Drive «Музыка» (подпапки артистов), затем **сразу удалять** локальные файлы. Постоянно только Google Drive. Без Telegram.

- 2026-08-06T10:54:03+03:00 **GEM / Polaris LSV — мануалы (постоянно):** источник сервисных мануалов, wiring, parts, bulletins — публичная коллекция Waev Brandfolder: **https://brandfolder.com/waev/service-support** (collection key `6mcqcc2h4ptjr9jngffg6q`). API: `GET https://brandfolder.com/api/v4/collections/6mcqcc2h4ptjr9jngffg6q/assets?search=GEM` → attachments URL. Owner’s manuals: https://www.gemcar.com/owners-manuals/ . Общая папка электрокаров: `Документы/Платы и модули/Электрокары/`. Локальный эталон e6 2017: `…/Электрокары/Polaris_GEM_e6_2017/` (SM **9940314 R02** 2016–2023). При другой модели GEM — Brandfolder + новая подпапка в `Электрокары/`; E-Z-GO/Club Car — туда же. Скрипт-образец: `…/Электрокары/Polaris_GEM_e6_2017/scripts/download_brandfolder.sh`.
- 2026-08-08: Kali БК / Audi B5 стенд — зажигание всегда ON; Comfort 0x46 отсутствует → двери по K-line недоступны.

- 2026-08-08T18:53:00+03:00 Музыка на Drive: **всегда** в `Музыка/<исполнитель>/`. Папку артиста **создавать**, если нет. Не класть треки в корень «Музыка». Temp → upload → удалить с Pi 5. Без Telegram.

- 2026-08-09T01:11:41+03:00 **Коммуналка Drive (постоянно):** каждый месяц проверять и добавлять новые чеки PDF и показания счётчиков; хранить ВСЕ чеки (не удалять). Корень — только папки услуг. CSV только со счётчиком. Авто: komunalka-drive-sync.timer / Проекты/komunalka/scripts/monthly-drive-sync.sh. Drive: https://drive.google.com/drive/folders/1zbPCmouSU8yJhr-tGwe5BKfQsRqeN14b
- 2026-08-09: Audi A4 B5 Y921OE — заводская АКПП 01N; МКПП поставил владелец сам. Диагностика K-line; CAN только был ECM↔TCM.

- 2026-08-10T15:05:00+03:00 **Бесперебойное питание — таблица производства (ЖЁСТКО):** https://docs.google.com/spreadsheets/d/1LYT9UffGU9oduk4KxUl2fp2ON5Rsf44N5MlePwECbA8/edit — ID `1LYT9UffGU9oduk4KxUl2fp2ON5Rsf44N5MlePwECbA8`, листы **Производство** / **Расходники**. По запросам про АКБ, инверторы, заказы, отгрузки, склад — **сначала читать эту таблицу** (Google MCP `sheets_read`). Правило: `ups-production-sheet.mdc`, справочник: `Документы/.cursor/GOOGLE_SERVICES.md`.

- 2026-08-16T21:54:00+03:00 **ЖЁСТКО (пока пользователь не попросит сменить):** модель по умолчанию — **Composer 2.5** (`composer-2.5`). Не Auto. Канон: `~/.cursor/cli-config.json`; обёртки `~/bin/agent` и `~/bin/agent-vpn`; `CURSOR_AGENT_MODEL` в `~/.config/cursor-agent.env`. Деплой: `cursor_bridge_patch/tmux-agent/set-composer-2.5-default.sh`.

- 2026-08-17T21:30:00+03:00 **Documents на Pi 5 — обзор изучен:** …

- 2026-08-28T16:15:00+03:00 **SILA VM II Premium+ 6.2K (Voltronic) — BMS CAN:** прог.05 **LIA** = протокол **Voltronic CAN** (не Pylon): 500k, 29-bit, INV шлёт `0x0CF10100`…`0x0CF1010F`, `0x0CF10220`, `0x0CF10400`/`10` (payload 0); BMS отвечает `0x0CF201xx`/`0x0CF202xx`/`0x0CF204xx`. **Pylontech** (BT=3) = отдельно `0x351`… (A11096). **User** = CAN молчит. Док: `Платы и модули/Солнечные_инверторы/SILA_VM_II_Premium_Plus_6.2K/notes/CAN_BMS_VOLTRONIC_LIA.md`; спека OEM 20220304.

- 2026-08-31T18:46:00+03:00 **ЖЁСТКО: Учёба Артём.** **Договоры и документы — ТОЛЬКО загруженные файлы на Drive**, искать и отвечать из них. Сайт — успеваемость/изменения. 09.02.07, раз в неделю.

- 2026-09-02T13:36:00+03:00 **GEM e6 BMC CAN-эмулятор v4 — РАБОТАЕТ:** неисправная VIN `5ACA6AGA3H0002115`, Pi5+RS485 CAN HAT 250k. Скрипт `Платы и модули/Электрокары/Polaris_GEM_e6_2017/scripts/can-bmc-emulate.py`. Приборка OK, DTC нет (P1824/P1827 ушли). Памятка: `…/notes/BMC_CAN_EMULATOR_v4_OK.md`. Запуск: `can-setup.sh --bitrate 250000` → `ai-tmux run gem-bmc-emu 'python3 …/can-bmc-emulate.py'`. Дальше: X3 p12 V-Out, реле, шунт.

- 2026-09-07T09:48:23+03:00 2026-09-07 ЖЁСТКО: с Pi3 **не** авточинить Pi5 (только по явной просьбе). На Pi3 `pi5-remote-watchdog.timer` disabled.

- 2026-09-07T11:42:57+03:00 2026-09-07 ЖЁСТКО: автопочин Pi5 stack **выключен**. `pi5-stack-watchdog.timer` на Pi5 — **disabled** (раньше каждые ~2 мин чинил xray/proxy/mvp и слал jarvis-need-user). Чинить Pi5 только по явной просьбе пользователя. С Pi3 remote тоже уже disabled.
- 2026-09-15T15:59:51 **Aqara CH-H01 3D65 ЭТАЛОН:** flip=3 + сток osd_orig, timestamp OK. Не крутить OSD-шрифты. Подтверждено пользователем 2026-09-15.
- 2026-09-16T08:48:06 **Aqara CH-H01:** дома с хабом+Apple TV motion OK; в гараже без хаба в сети — плитка «не отвечает», пуш может идти. Bool-патч не трогать.

- 2026-09-28T14:33:23+03:00 **ЖЁСТКО:** не плодить одинаковые копии файлов — каждый файл только в одном месте; генераторы пишут в одну папку, в соседних .md — ссылка на путь. Правило: `Документы/.cursor/rules/separate-folder-per-topic.mdc` §6.
- 2026-09-29T08:04:44+03:00 **АКБ + инвертор (Deye RW-F16 и аналоги):** в ответах про подключение/настройку АКБ **всегда отдельным явным шагом** называть связь BMS: PCS батареи №1 → BMS инвертора; между АКБ OUT → IN; у последней OUT и PCS свободны. Не вскользь.

- 2026-10-23T15:45:46+03:00 **ЖЁСТКО: пометка даты при изменениях.** При любой правке файла/дока/PDF — дата YYYY-MM-DD (шапка «Обновлено», редакция PDF, CHANGELOG). Правило: Документы/.cursor/rules/date-stamp-on-changes.mdc.

- 2026-10-28T21:09:29+03:00 2026-10-28 **Учёба Артём — профиль на Drive:** файл `00_Профиль_Артём.md` (id `1-oOJJE-Obtx2cV5M77TejKMjGZnU6HIq`) в папке «Учёба Артём»; ДР 20.06.2009, группа С-Ин-25, 09.02.07; курс Скултех/Квантастика — **не регистрироваться** (2026-10-28). Локально: `Проекты/artem-study-drive/data/`.

- 2026-10-30T15:48:00+03:00 **ЖЁСТКО: «моя батарея» = 4S** LiFePO4 230Ah, JK-B2A8S20P MAC `C8:47:80:53:0F:B6`, папка `Документы/Платы и модули/АКБ_LiFePO4_12V_230Ah/`. Настройка/BLE без явного 16S/ЭЛЬТАВР — только к ней. Не путать с JK_B2A20S20P (шаблон 16S). Правило: Documents/.cursor/rules/my-battery-4s.mdc.

- 2026-10-30T16:09:26+03:00 BLE-имя личной 4S JK (`C8:47:80:53:0F:B6`) = **AKB-4S-230** (записано reg 0x9B, 2026-10-30).

- 2026-10-31T19:59:32+03:00 **ЖЁСТКО:** в гараже (Pi3/Kali, 10.0.20.0/24) **НИКОГДА** не отключать Wi‑Fi (nmcli radio wifi off / rfkill / wlan down). Wi‑Fi GARAGE — основной выход в интернет и NetBird. Для BLE только txpower↓ или stop bluetoothd. Правило Cursor: Documents/.cursor/rules/garage-wifi-never-off.mdc (2026-10-31).

- 2026-11-08T16:37:37+03:00 2026-11-08 ЖЁСТКО: VPN на Pi5 (xray) должен работать всегда. Watchdog: `pi5-vpn-watchdog.timer` каждые 2 мин — только SOCKS 10808 + HTTP 10809; `pi5-stack-watchdog` (с Cursor Agent) остаётся disabled. HTTP-прокси upstream = 127.0.0.1:10808 (не NetBird Pi3).

- 2026-11-08T16:39:17+03:00 2026-11-08 ЖЁСТКО: VPN на Pi5 (xray) должен работать всегда. Watchdog: `pi5-vpn-watchdog.timer` каждые 2 мин — только SOCKS 10808 + HTTP 10809; `pi5-stack-watchdog` (с Cursor Agent) остаётся disabled. HTTP-прокси upstream = 127.0.0.1:10808 (не NetBird Pi3).

- 2026-11-08T16:46:57+03:00 2026-11-08 ЖЁСТКО: стабильный VPN Pi5 — xray Restart=always, ExecStartPre sync, proxy ждёт 10808, pi5-vpn-watchdog с проверкой exit IP 89.127.199.6, docker xray удалён.

- 2026-11-08T17:08:05+03:00 2026-11-08 ЖЁСТКО: VPS Cursor_ (130.17.8.47, Fornex #34-387109) = облачный Cursor Agent 24/7 **только SSH/CLI** (без PWA/8766/8767). SSH `ssh cursor-cloud` / `ssh cursor-cloud-shell` (user agent). Знания/ключи/Google токены синхронизированы. vpn-relay снят.

- 2026-11-08T17:23:09+03:00 SSH к облачному агенту: `ssh cursor-cloud` (чат Джарвис), `ssh cursor-cloud-shell` (shell). VPS 130.17.8.47 user agent.

- 2026-11-08T17:26:17+03:00 ЖЁСТКО: VPS Cursor_ (130.17.8.47) = только резервный Cursor Agent по SSH/CLI. PWA/сайты 8766·8767 отключены и замаскированы. Вход: `ssh cursor-cloud` (чат), `ssh cursor-cloud-shell` (shell). Не сайт.
- 2026-11-08T18:40:30+03:00 ЖЁСТКО: SSH-only **только** на VPS Cursor_ (130.17.8.47). Pi 5 PWA :8766/:8767 **не трогать** — основной веб-агент на работе остаётся.

---

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

