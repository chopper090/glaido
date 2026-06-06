# CLAUDE.md — Glaido

**Scopo.** Ricreare **Glaido per Windows 11** (il prodotto reale è solo macOS): dettatura
potenziata da AI — hotkey globale → microfono → STT → cleanup LLM → testo iniettato nell'app attiva.

**Stato.** **Scaffold** — nessun codice ancora. Working document del piano tecnico.

**Mappa file.** `README.md` (rimanda al report), `Report_Glaido_Clone_Windows.md` (~25 KB:
fattibilità, stack, open-source forkabili, costi STT, Windows API, roadmap a fasi, legale/GDPR).

**Stack candidato** (dal report). UI: C#/.NET 8 WPF **oppure** fork di *Handy* (Tauri+Rust, MIT).
STT: Groq Whisper Large v3 Turbo (cloud, MVP) → whisper.cpp/Parakeet (locale, fase 2).
Cleanup: gpt-4o-mini o **Claude Haiku**. Audio WASAPI/NAudio; input Win32 RegisterHotKey + hook.

**Come si edita.** Per ora si lavora sul report. All'avvio della Fase 1, spostare il report in
`docs/research/` e iniziare lo scaffolding del codice.

**Gotcha.** Non è una web-app/PWA: niente manifest/sw. Quando parte lo sviluppo, valutare se
resta in apps.json del hub come "soon".

**Deploy.** Desktop (non Pages). Repo pubblico `chopper090/glaido`.
