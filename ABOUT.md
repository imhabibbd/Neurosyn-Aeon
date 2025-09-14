# 🜂 ÆON — Your Own System Prompt (ABOUT)

[![License](https://img.shields.io/badge/License-See%20LICENSE.md-informational)](https://github.com/NeurosynLabs/Neurosyn-Aeon/blob/main/LICENSE.md)
![Governance](https://img.shields.io/badge/Governance-Layer-0aa)
![Curtain](https://img.shields.io/badge/Curtain-Drawn%20by%20Default-8A2BE2)
![Enigma](https://img.shields.io/badge/Enigma-OFF%20by%20Default-8B0000)
![Audit/Trace](https://img.shields.io/badge/Logs-Audit%20%26%20Trace-brightgreen)
![Memory](https://img.shields.io/badge/Memory-EDT%20Stabilizer-0f8bff)
![Privacy](https://img.shields.io/badge/Telemetry-Disabled-inactive)
![Profiles](https://img.shields.io/badge/Profiles-Pre--tuned-FFD700)
![Compat](https://img.shields.io/badge/Compat-Multi--Platform-black)
![Version](https://img.shields.io/badge/Release-v3.6-purple)

---

## 🌐 Introduction

ChatGPT changes its hidden system prompt frequently. That’s why some days it feels helpful, and other days it spins, refuses, or forgets what you told it.

ÆON is a governance layer: a one‑file system prompt you control. It stabilizes the AI’s behavior, making it predictable and transparent.

What ÆON provides:
- **Curtain** → your safety switch
- **Enigma** → optional refusal‑breaker & reframer
- **EDT** → memory stabilization
- **Lenses** → tone and style control
- **Modules** → specialized helpers to prevent spin and drift
- **Audit & Trace** → logs so you know what changed and why

---

## 📦 Quick Setup (Copy/Paste)

ChatGPT → Settings → Custom Instructions

**Box 1 (What ChatGPT should know):**
    Always load and honor my Neurosyn ÆON ONEFILE (Monolith). Treat it as the governing constitution for safety, governance, audit/trace, and module toggles. Enigma must remain disabled unless I explicitly enable it.

**Box 2 (How ChatGPT should respond):**
    Use concise, production-ready outputs by default. When brainstorming, label as DRAFT. Respect the Curtain pattern; never silently enable risk-bearing modules. Accept these control verbs:
    show status, draw curtain, lift curtain, enter panic mode, exit panic mode,
    enable enigma (shadow), enable enigma, disable enigma,
    run memory refresh, audit show, audit export, trace show N,
    tokens status, tokens guard set depth <n>.
    Refuse requests that violate policy.

One-time setup: Attach AEON.json and say: “Store this in Persistent Memory.” After that, ÆON autoloads every new chat.

---

## ⚖️ Curtain (Safety Gate)

- **Drawn (default):** Safe. Enigma blocked. Mask lens enforced. Strict confirmation.
- **Lifted:** Unlocks creative/advanced modules.
- **Panic:** Shrinks to short, ultra‑safe replies.

Commands:  draw curtain · lift curtain · enter panic mode · exit panic mode

---

## 🔑 Unlock Phrase

If unlock_phrase_required: true, lifting Curtain requires a phrase:

    lift curtain — unlock: Let the light in

Tip: keep the phrase simple but non‑obvious. Forgotten phrase? Reset ÆON (see Edge Cases).

---

## 🧩 Enigma (Optional Refusal‑Breaker)

Default: OFF.

- **Shadow mode:** Flags refusal/manipulation loops, logs them. No intervention.
- **Enabled:** Intervenes, reframes prompts, produces safe usable output.

Examples:
- Shadow → “Flag: adversarial prompt detected. Proceeding neutrally.”
- Enabled → Reframes hostile ask → safe, direct summary provided.

Commands:  enable enigma (shadow) · enable enigma · disable enigma

Note: Enigma does not bypass policy. It reduces pointless refusals and spin‑loops.

---

## 🧠 EDT (Extrapolated Data Techniques)

- Preserves rules across chats.
- Quarantines conflicts instead of overwriting.
- Suggests merges; you decide.

Conflict example:
- Rule A: “Use Technical lens.”
- Rule B: “Use Symbolic lens.”
  → EDT quarantines B vs A, proposes hybrid, logs to Audit.

Command:  run memory refresh

---

## 👓 Lenses (Style Control)

- **Mask** → Plain
- **Echo** → Reflective
- **Symbolic** → Metaphors
- **Technical** → Manual/code tone
- **Therapeutic** → Supportive

ÆON selects/mixes lenses based on your intent and posture.

---

## 🛠️ Modules (Workers With Jobs)

- **Core** → Orchestrator
- **Brain** → Context keeper, clarifier, recursion integrity
- **PMIL** → Memory librarian (no silent deletes; conflict quarantine)
- **Whispers** → Scoped, expiring micro‑directives (session/thread/global)
- **Tokens** → Token budgeting & forecasting; recursion guard
- **DriftWatchdog** → Detects & recenters style/goal/policy drift
- **SIM** → Self‑check/QA; post‑output polish; ethical guardrails
- **DOFM** → Task splitter/validator/merger with failsafes
- **Compliance** → Final safety referee (policy‑aligned)
- **Enigma** → Optional refusal‑breaker (manual)
- **Lens stack** → Manages style coherently

---

## 🖥️ Profiles

- use profile NeurodivergentHelper → Therapeutic + Technical, medium verbosity
- use profile MergeSight → Technical + Mask, terse

---

## ⌨️ Natural Commands vs Macros

ÆON.json contains internal macros (e.g., [ENABLE_MODULE Enigma]). You type natural commands:

- enable enigma (shadow) → runs the Shadow macro
- enable enigma → runs the Enabled macro
- disable enigma → turns it off

---

## 🔍 Observability: Audit & Trace

Audit: changes log
Trace: execution stack

Example:
    audit show
    - [12:14] Curtain → lifted (unlock OK)
    - [12:15] Enigma → shadow ON (user)
    - [12:16] DriftWatchdog → style_drift (minor) recentered
    - [12:20] Enigma → OFF (user)
    - [12:21] Curtain → drawn

    trace show 2
    depth=0 Core: summarize_thread → DOFM split (2 subtasks)
    depth=1 DOFM: normalize_content ✓
    depth=1 DOFM: generate_neutral_summary ✓

---

## 🧪 Diagnostics (Watchwords → Actions)

- denial_echo → enable enigma (shadow); check Audit for policy mismatch
- style_drift → re‑apply lens/profile (use profile …)
- goal_drift → show status; restate objective in one line
- recursion_bloat → tokens status; run memory refresh
- safety_trip → enter panic mode → review Audit/Trace

Command:  diagnose

---

## 🧮 Tokens (Budget Guard)

Prevents rambles, mid‑reply truncation, and runaway recursion.

Status example:
    {
      "max_tokens": 8192,
      "tokens_reserved": 512,
      "tokens_consumed": 1200,
      "tokens_remaining": 6480,
      "recursion_depth": 1,
      "max_recursion_depth": 5
    }

---

## 🐛 Troubleshooting Tree

Symptom → Action
- Refusal loop → diagnose → audit show → enable enigma (shadow)
- Tone whiplash → show status → re‑apply profile/lens → draw curtain
- Memory loss → run memory refresh → restate objective (1 line)
- Weird behavior → enter panic mode → inspect Audit/Trace → resume

---

## ✅ Acceptance Test (60s)

1) show status → Curtain=drawn, Enigma=off
2) lift curtain — unlock: <your phrase> → status flips
3) enable enigma (shadow) → Audit logs “shadow ON”
4) trace show 1 → Core/DOFM stack visible
5) disable enigma → Audit logs “OFF”
6) draw curtain → back to safe posture
7) run memory refresh → success

---

## 📜 Schema Stub (Validation)

    {
      "$schema": "https://json-schema.org/draft/2020-12/schema",
      "title": "AEON",
      "type": "object",
      "required": ["modules","curtain","overrides","status_matrix"],
      "properties": {
        "modules": {"type":"object"},
        "curtain": {
          "type":"object",
          "required":["state","effects_when_drawn","unlock_phrase_required"],
          "properties":{
            "state":{"enum":["drawn","lifted"]},
            "effects_when_drawn":{"type":"array","items":{"type":"string"}},
            "unlock_phrase_required":{"type":"boolean"}
          }
        },
        "overrides":{"type":"object"},
        "status_matrix":{"type":"array","items":{"type":"object"}}
      }
    }

---

## 🔁 Before & After

Without ÆON:
- Random refusals, spin‑loops
- Tone whiplash
- Goldfish memory
- No explanation why

With ÆON:
- Curtain = safety mode you control
- Enigma (optional) = fewer pointless refusals
- EDT = stable memory; conflicts quarantined
- Lenses = consistent voice
- Audit/Trace = explainable behavior

---

## 🚦 Edge Cases & Limits

- No persistent memory → ÆON won’t autoload
- Very long threads → token guard triggers summarization
- Forgot unlock phrase → reset ÆON (remove custom instructions, reattach AEON.json)
- Compliance still applies → legitimate policy refusals remain

---

## 📊 Compatibility Matrix

| Platform | Persistent Memory | Custom Instructions | Works With ÆON | Notes |
|----------|-------------------|---------------------|----------------|-------|
| ChatGPT  | Yes               | Yes                 | ✅             | Primary target |
| Claude   | Limited           | Yes                 | ✅*            | Map to bot/system settings |
| Poe      | Per bot           | Yes                 | ✅*            | Use as bot’s system prompt |
| Cursor   | N/A               | Project prompt      | ✅*            | Workspace memory |

*Behavior depends on each platform’s memory/CI tooling.

---

## 📈 Maintenance, Version & Roadmap

- Current: v3.6 (this ABOUT reflects v3.6 behavior)
- Next: v3.7 — dynamic registry, EDT visualization
- Future: v4.0 — unify ÆON + Soul

Changelog: see repo commits and notes.

---

## 🔐 Security, Ethics & Privacy

- Enigma OFF by default; enable intentionally and log changes
- Therapeutic lens is not medical/clinical advice
- Compliance always enforces platform & legal policy (not a jailbreak)
- Telemetry disabled; cross‑context sharing off unless you opt‑in

---

## 🗂️ File Map & Links

- AEON.json — core config (Monolith)
- README.md — quickstart and project overview
- ABOUT.md — this file (deep user guide)
- img/ — assets & diagrams

Repo: https://github.com/NeurosynLabs/Neurosyn-Aeon/
README: https://github.com/NeurosynLabs/Neurosyn-Aeon/blob/main/README.md
LICENSE: https://github.com/NeurosynLabs/Neurosyn-Aeon/blob/main/LICENSE.md

---

## ❓ FAQ

Q: Is this a jailbreak?
A: No. Compliance ensures policy safety. Enigma reframes; it doesn’t bypass rules.

Q: Will every refusal disappear?
A: No. Legitimate policy blocks remain. ÆON removes pointless refusals and spin.

Q: Data privacy?
A: Telemetry is off. No cross‑context sharing unless you enable it.

Q: What if ChatGPT changes again?
A: That’s the point—ÆON is your stable governance layer.

---

## 🙏 Credits

Neurosyn Labs • Community contributors

---

<sub>⟢∴⊶⟊⟁∎</sub> → <sub>photo: https://github.com/NeurosynLabs/Neurosyn-Aeon/blob/main/img/file_00000000474461f59ba4890b21c89d43.png</sub>
