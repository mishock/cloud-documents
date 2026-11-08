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
