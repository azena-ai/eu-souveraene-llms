# EU-souveräne LLMs — leistungsfähige KI ohne Datentransfer in die USA

> Herstellerneutraler Überblick: Welche leistungsfähigen Sprachmodelle kann ein
> deutsches/europäisches Unternehmen 2026 **DSGVO-konform** betreiben, ohne Daten in die USA
> zu schicken? Mit Lizenzen, Hosting-Optionen und der rechtlichen Realität — jeder Fakt mit Quelle.

Gepflegt von **[azena](https://azena.ai)** — KI-Boutique aus Stuttgart, die genau solche Systeme
für den Mittelstand baut. **Kein Rechtsrat — eine Arbeitsgrundlage.** Stand: **Mitte 2026**.
Korrekturen & PRs willkommen.

---

## In 60 Sekunden

Es gibt zwei saubere Wege zu „keine Daten in die USA":

1. **Offene Gewichte selbst hosten** auf eigener oder EU-Cloud-Infrastruktur. Dann fließen *keine*
   Inferenzdaten an den Modellhersteller — entscheidend ist nur die **Lizenz**, nicht die Herkunft
   des Herstellers. Top-Optionen: **Mistral** (Apache-Modelle), **Teuken/OpenGPT-X**, **EuroLLM**,
   **Qwen**, **DeepSeek**.
2. **Einen in der EU ansässigen Managed-Anbieter** nutzen: **Mistral La Plateforme, IONOS,
   OVHcloud, Scaleway**. Kein US-CLOUD-Act-Zugriff, Datenresidenz in der EU.

Der **verbreitete Irrtum**: Die „EU-Region" eines US-Anbieters (Azure, AWS) löst das Problem
**nicht** — der US CLOUD Act greift unabhängig vom Speicherort. Dazu unten mehr.

---

## 1. Offene Gewichte selbst hosten — die Lizenz entscheidet

Wenn ihr heruntergeladene Gewichte auf eurer eigenen oder einer EU-Infrastruktur betreibt, gibt es
**keinen Datentransfer** an den Hersteller — auch nicht bei Modellen aus China oder den USA. Die
Server-Herkunft betrifft nur die *gehostete API* des Herstellers, nicht lokal laufende Gewichte.
Maßgeblich für den Eigenbetrieb ist deshalb die **Lizenz**.

| Modell | Herkunft | Lizenz (kommerziell?) | Größe | Anmerkung |
|---|---|---|---|---|
| **Mistral Large 3** | 🇫🇷 EU | **Apache 2.0** ✅ | MoE 675B/41B aktiv | permissives Flaggschiff |
| **Ministral 3** (3–14B) | 🇫🇷 EU | **Apache 2.0** ✅ | dense | self-host-freundlich |
| Mistral Small 3.x, Magistral Small, Devstral | 🇫🇷 EU | **Apache 2.0** ✅ | 7–24B | breit nutzbar |
| **Teuken-7B** (OpenGPT-X) | 🇪🇺 DE/EU | **Apache 2.0** ✅ | 7B | alle 24 EU-Amtssprachen, EU-trainiert |
| **EuroLLM-22B** | 🇪🇺 EU-Konsortium | **Apache 2.0** ✅ | 22B | 35 Sprachen |
| **Salamandra / ALIA-40B** | 🇪🇸 BSC | **Apache 2.0** ✅ | 2–40B | europäisch trainiert |
| **Qwen3** (0.6–235B) | 🇨🇳 Alibaba | **Apache 2.0** ✅ | dense + MoE | permissiv; lokal datenschutzunkritisch |
| **DeepSeek-R1** | 🇨🇳 DeepSeek | **MIT** ✅ | 671B/37B aktiv | starkes Reasoning |
| ⚠️ **Mistral Large 2 / Pixtral Large** | 🇫🇷 EU | **MRL — nicht kommerziell** ❌ | — | **NICHT** Apache — Falle! |
| ⚠️ **Codestral 22B v0.1** | 🇫🇷 EU | **MNPL — nicht kommerziell** ❌ | 22B | spätere Versionen wurden umlizenziert |
| ⚠️ **Aleph Alpha Pharia-1 7B** | 🇩🇪 DE | **Open Aleph License — nur Forschung** ❌ | 7B | kommerziell nur per Vertrag |
| ⚠️ **Meta Llama 4** | 🇺🇸 USA | **Llama Community License** (kein OSI) ❌ | MoE | **EU-Sperre für multimodale Modelle** (s.u.) |

### Zwei Fallen, die teuer werden

- **Nicht alle „offenen" Mistral-Modelle sind Apache 2.0.** *Mistral Large 2* und *Pixtral Large*
  stehen unter der **Mistral Research License (MRL)**, *Codestral 22B v0.1* unter der **MNPL** —
  beide **nicht für die kommerzielle Produktion**. Prüft den HF-Lizenz-Tag, nicht den Ruf.
- **Llama 4 ist für EU-Unternehmen teilweise gesperrt.** Wörtlich aus dem Lizenztext: die multimodalen
  Llama-4-Modelle werden Nutzern „domiciled in … the European Union" bzw. mit Hauptsitz in der EU
  **nicht** lizenziert. Dazu greift ab >700 Mio. monatlich aktiven Nutzern eine Sonderlizenzpflicht.
  → [Lizenztext](https://github.com/meta-llama/llama-models/blob/main/models/llama4/LICENSE)

**Wirklich „EU-souverän" (EU-Herkunft *und* permissive Lizenz):** Mistral (Apache-Modelle),
Teuken/OpenGPT-X, EuroLLM, Salamandra/ALIA. Qwen und DeepSeek sind nicht EU-Herkunft, beim
**Self-Hosting** aber datenschutzunkritisch, weil die Gewichte lokal laufen.

## 2. Managed Inference in der EU — Daten bleiben in der EU

Wer nicht selbst hosten will, kann einen Anbieter nutzen, der das Modell betreibt und die Daten in
der EU hält. Entscheidend ist hier der **Unternehmenssitz** des Anbieters (wegen CLOUD Act, §3).

**Echte EU-Headquarter (kein CLOUD-Act-Zugriff):**

| Anbieter | Sitz | Datenresidenz | Modelle |
|---|---|---|---|
| **Mistral La Plateforme** | 🇫🇷 | **EU per Default**, kein Training auf API-Daten, Logs 30 Tage; DPA mit SCC | eigene Mistral-Modelle |
| **IONOS AI Model Hub** | 🇩🇪 | „Daten verlassen Deutschland nicht", ISO 27001 | Llama 3, Mistral, Mixtral, OpenGPT-X |
| **OVHcloud AI Endpoints** | 🇫🇷 | „Zero data retention", kein Training auf Nutzerdaten | Llama 3.3 70B, Mixtral, DeepSeek-R1, Whisper |
| **Scaleway Generative APIs** | 🇫🇷 | FR-Rechenzentren, ISO 27001/17/18, SOC 2 | Llama 3, Mistral, Mixtral |
| **Nebius AI Studio** | 🇳🇱 | EU-Hosting wählbar (Standort pro Modell ausgewiesen) | Llama, Mistral, Qwen, Nemo |

> *DPA-Detailtexte von OVHcloud und Scaleway konnten nicht final verifiziert werden — vor
> Vertragsschluss die jeweilige Auftragsverarbeitungs-Vorlage prüfen.*
> *Nebius ist die 2024 umbenannte Yandex N.V. (nach Verkauf aller Russland-Assets, NL-Sitz) —
> rechtlich kein US-Risiko, aber eine Governance-Nuance, die man kennen sollte.*

**US-Anbieter mit EU-Region (CLOUD-Act-relevant — siehe §3):**

| Anbieter | EU-Mechanismus | Caveat |
|---|---|---|
| **Azure OpenAI** | „EU Data Zone" + Microsoft „EU Data Boundary" | Microsoft = US-Konzern → CLOUD Act bleibt |
| **AWS Bedrock** | EU-Regionen Frankfurt/Irland | US-Konzern → CLOUD Act bleibt |
| **AWS European Sovereign Cloud** | **GA seit Jan 2026**, erste Region Brandenburg, separat EU-betrieben | Bedrock dort **nur Amazon-Nova-Modelle** zum Start |

Die wichtigste Neuerung Mitte 2026 ist die **AWS European Sovereign Cloud** (EU-betriebene, separate
Partition) — die Modellauswahl ist dort aber noch dünn.

## 3. Die rechtliche Realität: Warum „EU-Region" oft nicht reicht

Das ist der Teil, den die meisten falsch verstehen.

- **US CLOUD Act (2018):** zwingt **US-ansässige Anbieter**, Daten in ihrer „possession, custody, or
  control" herauszugeben — **unabhängig vom physischen Speicherort**. Eine EU-Region eines
  US-Anbieters beseitigt dieses Risiko also **nicht**.
  ([AWS zum CLOUD Act](https://aws.amazon.com/compliance/cloud-act/)) Microsoft France bestätigte 2025
  vor dem französischen Senat unter Eid, keine Garantie gegen US-Behördenzugriff selbst bei FR-Hosting
  geben zu können.
- **EU-US Data Privacy Framework (DPF):** Angemessenheitsbeschluss vom 10. Juli 2023, **Mitte 2026
  weiterhin in Kraft** — aber **angefochten**: Das EuG wies die Klage *Latombe* (T-553/23) am
  3. Sep 2025 ab; das **Rechtsmittel beim EuGH (Rs. C-703/25 P)** ist Mitte 2026 noch **anhängig**.
  Ein „Schrems III"-Urteil, das den DPF kippt, gibt es bislang **nicht**. Strukturell fragil bleibt
  der DPF, weil er auf der per Dekret widerrufbaren **Executive Order 14086** fußt und das
  US-Aufsichtsgremium PCLOB Anfang 2025 sein Quorum verlor. `[strittig/offen]`
- **DSGVO Art. 44 ff. + Schrems II (2020):** Jeder Transfer in ein Drittland (inkl. Fernzugriff)
  braucht eine Rechtsgrundlage — Angemessenheitsbeschluss oder **Standardvertragsklauseln (SCC)** plus
  ein **Transfer Impact Assessment**.
- **Verschlüsselung hilft hier nicht:** Die EDPB-Empfehlungen 01/2020 nennen starke Verschlüsselung mit
  ausschließlich im EWR gehaltenen Schlüsseln als wirksame Zusatzmaßnahme — **aber** LLM-Inferenz
  braucht den **Klartext** zur Verarbeitung. Damit greift diese technische Maßnahme nicht; der
  Transfer muss vermieden, nicht abgesichert werden.

> **Wichtig zur Abgrenzung:** Der **EU AI Act** regelt Risiko und Transparenz — **nicht** die
> Datenresidenz. Wo eure Daten liegen müssen, ergibt sich aus der **DSGVO**, nicht aus dem AI Act.
> (Zum AI Act: unser [EU-AI-Act-Leitfaden](https://github.com/azena-ai/eu-ai-act-mittelstand).)

**Fazit:** Der sicherste Weg zu „keine Daten in die USA" ist **nicht** die EU-Region eines
US-Anbieters, sondern **(a)** Self-Hosting offener Gewichte oder **(b)** ein EU-headquartierter Anbieter.

## 4. Deutsche & europäische Souveränitäts-Landschaft (Mitte 2026)

- **Aleph Alpha (Heidelberg)** hat sich 2024 vom Rennen um immer größere Foundation-Models
  verabschiedet und auf die Enterprise-Plattform **PhariaAI** verlagert. Im **April 2026** wurde die
  **Fusion mit dem kanadischen Cohere** angekündigt (transatlantische „Sovereign-AI"-Allianz, Schwarz-
  Gruppe als Investor; Abschluss vorbehaltlich Regulierung). Aleph Alpha ist damit **nicht mehr der
  eigenständige deutsche LLM-Champion**, sondern Teil eines Cohere-geführten Verbunds.
- **Deutsche Telekom + NVIDIA** bauen eine „Industrial AI Cloud" (AI-Factory München, live Q1 2026),
  **SAP** liefert den App-Layer. `[teils sekundär belegt]`
- **Schwarz Digits (StackIT) + SAP** bieten souveräne DE-Cloud-Infrastruktur.
- **EU „InvestAI"** (Feb 2025): 20 Mrd € für mehrere KI-Gigafactories auf EU-Boden.

Die Richtung ist klar: souveräne Infrastruktur entsteht — aber wer **heute** souverän bauen will,
greift zu offenen Gewichten oder einem EU-Anbieter (§§1–2), nicht auf Ankündigungen.

---

## Entscheidungs-Framework

| Euer Bedarf | Empfehlung |
|---|---|
| **Maximale Souveränität, null US-Risiko, volle Datenkontrolle** | Offene Apache-2.0/MIT-Gewichte **selbst hosten** (Mistral, Teuken, EuroLLM, Qwen, DeepSeek) auf eigener/EU-Cloud-Infra. Kein Transfer, kein DPA nötig. |
| **Managed, aber kein US-Zugriff** | EU-headquartierter Anbieter: **Mistral La Plateforme, IONOS, OVHcloud, Scaleway** (DPA mit SCC). |
| **Bereits in Azure/AWS, EU-Region genügt euch** | Möglich mit DPA — aber **CLOUD-Act-Restrisiko** und angefochtene DPF-Adäquanz bewusst dokumentieren (Transfer Impact Assessment). |
| **Erst verstehen, was geht** | Klein anfangen mit einem self-hosted 7–24B-Modell (Ministral 3, Teuken-7B) auf einer EU-GPU-Instanz. |

## Quellen (Auswahl)

- Mistral-Lizenzen & La Plateforme: <https://mistral.ai/news/mistral-3> · <https://legal.mistral.ai>
- Llama-4-Lizenz (EU-Klausel): <https://github.com/meta-llama/llama-models/blob/main/models/llama4/LICENSE>
- DeepSeek-R1 (MIT): <https://huggingface.co/deepseek-ai/DeepSeek-R1>
- Qwen3 (Apache 2.0): <https://huggingface.co/Qwen/Qwen3-235B-A22B>
- Teuken / OpenGPT-X: <https://opengpt-x.de> · EuroLLM: <https://huggingface.co/utter-project/EuroLLM-22B>
- US CLOUD Act: <https://aws.amazon.com/compliance/cloud-act/>
- DPF-Verfahren (EuG T-553/23, EuGH C-703/25 P): EUR-Lex CELEX 62023TJ0553 / 62025CN0703
- AWS European Sovereign Cloud: <https://aws.amazon.com/europe/sovereign-cloud/>

> **Methodik:** Fakten über mehrere Recherchequellen erhoben und die riskanten Aussagen
> (Lizenzen, EU-Sperren, Rechtslage) adversarial gegen Primärquellen gegengeprüft. Als `[unklar]`
> bzw. `[strittig]` markierte Punkte sind bewusst nicht als Gewissheit dargestellt. Modellversionen,
> die nur auf Aggregator-Seiten kursierten, wurden **nicht** übernommen. Förderrecht und Rechtsprechung
> ändern sich — vor Entscheidungen die verlinkte Primärquelle prüfen.

**Korrekturen willkommen** — Issue oder PR mit Quellenangabe.

---

<sub>Gepflegt von <a href="https://azena.ai"><b>azena</b></a> · maßgefertigte, EU-souveräne KI für den
deutschen Mittelstand · Stuttgart · Kayra Labs GmbH i. G. · Kein Rechts- oder Steuerrat.</sub>
