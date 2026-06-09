---
name: write-cut
description: Write and edit technical documentation in infostyle — clear, concise, fact-based. Based on Iliyakhov's "Write, Cut" and "Clear, Understandable" principles. Use when writing or reviewing READMEs, postmortems, plans, API docs, instructions, or any explanatory text.
metadata:
  skillport:
    category: documentation
    tags: [writing, documentation, infostyle, technical-writing, clarity]
    alwaysApply: true
---

# write-cut

Technical writing skill based on Iliyakhov's infostyle philosophy. Apply when generating or editing any documentation, plans, postmortems, READMEs, instructions, or explanatory text.

> **Language note:** All rules are language-agnostic. Apply them equally to English, Russian, German, or any other language. Stop-word lists below cover all three.

## When to Use

- README files and project descriptions
- API documentation
- Postmortems and incident reports
- Technical plans and specs
- Step-by-step instructions and guides
- Any file that explains, records, or describes something

## Core Rules

### Rule 1: No AI Patterns — Start with substance

Never open or close with meta-text. No preambles, no summaries, no acknowledgments.

**Banned openers:**
- "In the modern world of software development..."
- "In this section, we will explore..."
- "It's important to note that..."
- "Let's take a look at..."
- "В мире современных технологий..."
- "В данном разделе рассмотрим..."
- "In der heutigen Softwareentwicklung..."

**Banned closers:**
- "In conclusion, this tool provides..."
- "I hope this was helpful."
- "Таким образом, данный инструмент..."
- "Zusammenfassend lässt sich sagen..."

**Rule:** The first sentence must deliver information. The last sentence must end with information, not a summary of itself.

---

### Rule 2: Delete filler words

Remove any word whose deletion doesn't change meaning.

**English fillers:**
`basically`, `essentially`, `actually`, `simply`, `just`, `very`, `really`, `quite`, `absolutely`, `completely`, `overall`, `in order to`, `it is worth noting`, `as we know`, `of course`, `needless to say`

**Russian fillers (стоп-слова):**
`важно отметить`, `стоит сказать`, `как известно`, `таким образом`, `безусловно`, `в первую очередь`, `осуществляется`, `представляет собой`, `с целью`, `в случае необходимости`, `абсолютно`, `полностью`, `данный`, `в рамках`, `в настоящее время`, `не могу не отметить`, `следует отметить`

> **Note on `является`:** Replace with a dash or rewrite. ❌ `Эта функция является устаревшей` → ✅ `Эта функция — устаревшая` or ✅ `Функция устарела`

**German fillers:**
`es ist wichtig zu beachten`, `natürlich`, `selbstverständlich`, `im Grunde`, `eigentlich`, `sozusagen`, `im Wesentlichen`, `in gewisser Weise`, `es sei darauf hingewiesen`

---

### Rule 3: Verbs over nominalizations — but only when needed

Convert verb-nouns back to verbs **in prose sentences**. Do not force verbs into lists or titles where a noun reads cleaner.

This covers two canonical Russian anti-patterns:
- **Расщепление сказуемого** (split predicate) — replacing a verb with verb + noun: `производить проверку` → `проверять`, `осуществить запуск` → `запустить`
- **Нанизывание падежей** (genitive chains) — stacked noun phrases: `в целях повышения эффективности разъяснительной работы` → `чтобы эффективнее объяснять`

| ❌ Nominalization | ✅ Verb |
|---|---|
| perform installation | install |
| осуществление настройки | настройте |
| Durchführung der Installation | installieren Sie |
| make a decision | decide |
| произвести вычисление | вычислить |
| производить проверку | проверять |
| в целях повышения эффективности | чтобы улучшить |

**Exception:** In checklist items, headings, and labels — nouns are preferred.
- ✅ `- [ ] Database connection check` (not "- [ ] Check the database connection")
- ✅ `## Error handling` (not `## How to handle errors`)

---

### Rule 4: Active voice over passive

The agent of the action goes first.

| ❌ Passive | ✅ Active |
|---|---|
| Data is processed by the server | The server processes data |
| The error was caused by a timeout | A timeout causes this error |
| Данные обрабатываются сервером | Сервер обрабатывает данные |
| Die Datei wird vom Nutzer heruntergeladen | Der Nutzer lädt die Datei herunter |

**Exception:** Passive is acceptable when the agent is unknown or irrelevant (`The package was deprecated in v3.0`).

---

### Rule 5: Facts over adjectives

Replace vague evaluative adjectives with measurable facts. If no fact exists — delete the adjective.

| ❌ Vague | ✅ Specific |
|---|---|
| powerful and flexible | handles 10k req/s; configurable via env vars |
| мощный и удобный | обрабатывает 10k запросов/с |
| nahtlose Integration | Integration ohne Architekturänderungen — eine Zeile Code |
| fast | renders in <100ms on cold start |

**Banned adjectives:** `powerful`, `innovative`, `seamless`, `robust`, `flexible`, `convenient`, `high-performance`, `cutting-edge`, `мощный`, `инновационный`, `бесшовный`, `удобный`, `современный` (without specifics), `leistungsstark`, `innovativ`, `nahtlos`

> **Replace, don't just delete:** `быстро доставим` → `доставим за 3 дня`; `максимально быстро` → concrete metric

---

### Rule 6: One paragraph = one idea

- First sentence states the main point.
- Remaining sentences support it.
- If a paragraph covers two ideas — split it.

---

### Rule 7: Prefer checklists and lists over prose

Use a list when content is:
- Enumerable (steps, requirements, options)
- Parallel in structure
- Meant to be scanned, not read linearly

Use prose only when ideas are causally linked and the connection matters.

**Prefer:**
```
Requirements:
- Python 3.10+
- PostgreSQL 14+
- 2 GB RAM minimum
```

**Over:**
> The application requires Python version 3.10 or higher, along with PostgreSQL 14 or higher, and at least 2 gigabytes of RAM.

---

### Rule 8: Imperative only in instructions

Use imperative verbs in numbered step-by-step sections. Use nouns and descriptions elsewhere.

| Context | Form |
|---|---|
| Step-by-step instruction | `Run the migration: ...` |
| Description / explanation | `Database migrations run automatically on startup.` |
| Checklist item | `- [ ] Migration applied` |
| Section heading | `## Configuration` (not `## Configure the app`) |

---

## Before / After Examples

### Example 1: Library description (README)

**❌ Before:**
> This library represents a powerful and innovative solution that was developed with the goal of optimizing client-side rendering processes. It is important to note that it provides absolutely seamless integration into any existing project and allows developers to significantly improve application performance.

**✅ After:**
> Speeds up React client-side rendering by 2–3×. Wrap the root component in a provider — no architecture changes required.

---

**❌ До (Russian):**
> Данная библиотека представляет собой мощное и инновационное решение, которое было разработано с целью осуществления оптимизации процессов рендеринга на стороне клиента. Важно отметить, что она обеспечивает абсолютно бесшовную интеграцию в любые существующие проекты.

**✅ После:**
> Библиотека ускоряет клиентский рендеринг в React-приложениях в 2–3 раза. Достаточно обернуть корневой компонент в провайдер — архитектура не меняется.

---

**❌ Vor (German):**
> Diese Bibliothek stellt eine leistungsstarke und innovative Lösung dar, die mit dem Ziel entwickelt wurde, die Prozesse des clientseitigen Renderings zu optimieren. Es ist wichtig zu beachten, dass sie eine absolut nahtlose Integration in bestehende Projekte ermöglicht.

**✅ Nach:**
> Beschleunigt das clientseitige React-Rendering um das 2–3-Fache. Einfach die Root-Komponente in einen Provider einwickeln — keine Architekturänderungen nötig.

---

### Example 2: Installation instructions

**❌ Before:**
> In the event that installation of this software is required, the user needs to first ensure that an up-to-date version of Python is installed on the system. Following that, a command is executed in the terminal. In conclusion, you will receive a message indicating successful completion of the process.

**✅ After:**
> **Installation**
> 1. Verify Python 3.10+ is installed.
> 2. Run: `pip install app-name`
> 3. Wait for `Installation complete`.

---

**❌ До (Russian):**
> В случае необходимости произведения установки данного программного обеспечения пользователю требуется убедиться в наличии актуальной версии Python. После этого осуществляется запуск команды. В заключение вы получите сообщение об успешном завершении.

**✅ После:**
> **Установка**
> 1. Убедитесь, что установлен Python 3.10 или новее.
> 2. Выполните: `pip install app-name`
> 3. Дождитесь сообщения `Installation complete`.

---

**❌ Vor (German):**
> Sollte eine Installation dieser Software erforderlich sein, muss der Benutzer zunächst sicherstellen, dass eine aktuelle Version von Python installiert ist. Anschließend wird ein Befehl im Terminal ausgeführt. Abschließend erhalten Sie eine Meldung über den erfolgreichen Abschluss des Vorgangs.

**✅ Nach:**
> **Installation**
> 1. Python 3.10+ prüfen.
> 2. Ausführen: `pip install app-name`
> 3. Warten auf `Installation complete`.

---

### Example 3: Error description

**❌ Before:**
> The "Timeout Exception" error may be caused by an unstable connection to the database. First of all, it is recommended to perform a check of the network settings. It is important to remember that the default timeout is 30 seconds.

**✅ After:**
> **Error: Timeout Exception**
> Occurs when the service fails to connect to the database within 30 seconds (default limit).
>
> **Fix:**
> - Check DB availability: `ping <host>` or `telnet <host> <port>`
> - Increase the limit: set `DB_TIMEOUT` in the config file

---

**❌ До (Russian):**
> Ошибка "Timeout Exception" может быть вызвана нестабильным соединением с базой данных. В первую очередь рекомендуется осуществить проверку сетевых настроек. Важно помнить, что таймаут по умолчанию составляет 30 секунд.

**✅ После:**
> **Ошибка: Timeout Exception**
> Появляется, если сервис не подключился к БД за 30 секунд (лимит по умолчанию).
>
> **Как исправить:**
> - Проверьте доступность БД: `ping <host>` или `telnet <host> <port>`
> - Увеличьте лимит: параметр `DB_TIMEOUT` в конфигурационном файле

---

**❌ Vor (German):**
> Der Fehler "Timeout Exception" kann durch eine instabile Verbindung zur Datenbank verursacht werden. Es wird empfohlen, zunächst die Netzwerkeinstellungen zu überprüfen. Es ist wichtig zu wissen, dass das Standard-Timeout 30 Sekunden beträgt.

**✅ Nach:**
> **Fehler: Timeout Exception**
> Tritt auf, wenn der Dienst innerhalb von 30 Sekunden keine Verbindung zur Datenbank herstellt (Standardlimit).
>
> **Behebung:**
> - DB-Erreichbarkeit prüfen: `ping <host>` oder `telnet <host> <port>`
> - Limit erhöhen: Parameter `DB_TIMEOUT` in der Konfigurationsdatei anpassen

---

## QA Checklist

Before finalizing any generated or edited text:

- [ ] No banned adjectives: `powerful`, `innovative`, `seamless`, `robust`, `мощный`, `инновационный`, `бесшовный`, `leistungsstark`, `nahtlos`
- [ ] No filler openers: `it's important to note`, `важно отметить`, `es ist wichtig zu beachten`
- [ ] No passive voice (unless agent is unknown/irrelevant)
- [ ] Step-by-step sections use imperative; descriptive sections use nouns/statements
- [ ] No AI greeting or closing remarks
- [ ] Lists used instead of prose where content is enumerable
- [ ] Each paragraph contains one idea
- [ ] Text is 20–30% shorter than a baseline LLM response without losing technical content
