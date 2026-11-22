# Tesla Toolbox — довідник сигналів / Signal Reference

🇺🇦 [Українська](#українська) | 🇬🇧 [English](#english)

---

## Українська

Інтерактивний довідник CAN-сигналів Tesla Model 3, зібраний зі знімку `Metadata`,
який повертає **Tesla Toolbox Proxy** (`ws://localhost:7003/sui/api/ws`, запит `{"type":"List"}`).

Довідник містить **3787 сигналів** у **47 секціях** (BMS, PCS, VCFRONT, VCLEFT,
VCRIGHT, VCSEC, DAS, TPMS, RCM, UI та інші) — назва секції визначається як префікс
імені сигналу до першого символу `_` (наприклад, `BMS_brickVoltageMin` → `BMS`).

Для кожного сигналу доступні:
- тип (`number`, `enum`, `bool`);
- одиниця вимірювання, мінімум, максимум, період оновлення (cycle time);
- опис англійською та українською мовою;
- розшифровка значень для сигналів типу `enum`.

### Файли

- `values.html` — сторінка довідника: пошук, фільтри за секцією/типом,
  перемикач мови інтерфейсу **UA / ENG** (праворуч у хедері).
- `values.js` — дані сигналів (`TESLA_SIGNAL_SECTIONS`), **автоматично генеруються**
  скриптом `scripts/build-values.mjs` зі знімку `Metadata` — вручну не редагувати.

### Як користуватись

Просто відкрийте `values.html` у браузері — жодного збирання чи сервера не потрібно.

### Перегенерація даних

```
node scripts/build-values.mjs <дамп-metadata.json>
```

---

## English

An interactive CAN signal reference for the Tesla Model 3, built from a `Metadata`
snapshot returned by the **Tesla Toolbox Proxy** (`ws://localhost:7003/sui/api/ws`,
request `{"type":"List"}`).

The reference covers **3787 signals** across **47 sections** (BMS, PCS, VCFRONT,
VCLEFT, VCRIGHT, VCSEC, DAS, TPMS, RCM, UI, and more) — a section name is the
signal name's prefix up to the first `_` (e.g. `BMS_brickVoltageMin` → `BMS`).

Each signal includes:
- type (`number`, `enum`, `bool`);
- unit, min, max, cycle time;
- description in both English and Ukrainian;
- value breakdown for `enum` signals.

### Files

- `values.html` — the reference page: search, section/type filters, and a
  **UA / ENG** interface language switch (top-right of the header).
- `values.js` — the signal data (`TESLA_SIGNAL_SECTIONS`), **auto-generated**
  by `scripts/build-values.mjs` from a `Metadata` snapshot — do not edit by hand.

### Usage

Just open `values.html` in a browser — no build step or server required.

### Regenerating the data

```
node scripts/build-values.mjs <metadata-dump.json>
```
