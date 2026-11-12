# EU-souveräne LLMs — leistungsfähige KI mit Datenresidenz in der EU

> Herstellerneutraler Überblick: Welche leistungsfähigen Sprachmodelle kann ein
> deutsches/europäisches Unternehmen 2026 **DSGVO-konform mit voller Datenkontrolle** betreiben?
> Mit Lizenzen, EU-Hosting-Optionen und der rechtlichen Einordnung — jeder Fakt mit Quelle.

Gepflegt von **[azena](https://azena.ai)** — KI-Boutique aus Stuttgart, die genau solche Systeme
für den Mittelstand baut. **Kein Rechtsrat — eine Arbeitsgrundlage.** Stand: **Mitte 2026**.
Korrekturen & PRs willkommen.

Es geht hier um **EU-Datensouveränität und Datenresidenz** — also darum, bewusst zu entscheiden,
wo und in welchem Rechtsraum die eigenen Daten verarbeitet werden. Das ist eine Stärke, keine
Abgrenzung: viele der besten offenen Modelle und Cloud-Anbieter sind international, und das ist gut so.

---

## In 60 Sekunden

Es gibt zwei saubere Wege zu voller Datenkontrolle mit Verarbeitung in der EU:

1. **Offene Gewichte selbst hosten** auf eigener oder EU-Cloud-Infrastruktur. Dann fließen *keine*
   Inferenzdaten an den Modellhersteller ab — entscheidend ist nur die **Lizenz**, nicht die Herkunft
   des Herstellers. Top-Optionen: **Mistral** (Apache-Modelle), **Teuken/OpenGPT-X**, **EuroLLM**,
   **Qwen**, **DeepSeek**.
2. **Einen in der EU ansässigen Managed-Anbieter** nutzen: **Mistral La Plateforme, IONOS,
   OVHcloud, Scaleway** — mit Datenresidenz in der EU.

Wichtig zu verstehen: Eine „EU-Region" allein sagt noch nichts über den **Rechtsraum**, dem ein
Anbieter unterliegt. Wer echte Datenresidenz braucht, kalkuliert das mit ein — dazu unten mehr.

---

## 1. Offene Gewichte selbst hosten — die Lizenz entscheidet

Wenn ihr heruntergeladene Gewichte auf eurer eigenen oder einer EU-Infrastruktur betreibt, gibt es
**keinen Datenabfluss** an den Hersteller — auch nicht bei Modellen aus den USA oder China. Die
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
| ⚠️ **Codestral 22B v0.1** | 🇫🇷 EU | **MNPL — nicht kommerziell** ❌ | 22B | spätere Versionen umlizenziert |
| ⚠️ **Aleph Alpha Pharia-1 7B** | 🇩🇪 DE | **Open Aleph License — nur Forschung** ❌ | 7B | kommerziell nur per Vertrag |
| ⚠️ **Meta Llama 4** | 🇺🇸 USA | **Llama Community License** (kein OSI) ❌ | MoE | EU-Sperre für multimodale Modelle (s.u.) |

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

## 2. Managed Inference mit Datenresidenz in der EU

Wer nicht selbst hosten will, kann einen Anbieter nutzen, der das Modell betreibt und die Daten in
der EU verarbeitet. Für die Datenresidenz ist hier der **Unternehmenssitz** des Anbieters ein
wichtiger Faktor (siehe §3).

**In der EU ansässig, EU-Datenresidenz:**

| Anbieter | Sitz | Datenresidenz | Modelle |
|---|---|---|---|
| **Mistral La Plateforme** | 🇫🇷 | **EU per Default**, kein Training auf API-Daten, Logs 30 Tage; DPA mit SCC | eigene Mistral-Modelle |
| **IONOS AI Model Hub** | 🇩🇪 | „Daten verlassen Deutschland nicht", ISO 27001 | Llama 3, Mistral, Mixtral, OpenGPT-X |
| **Lyceum** | 🇩🇪 | Serverless-Modelle laufen in Paris und Finnland; Prompts und Ausgaben werden nicht gespeichert, kein Training; DPA als Anhang der AGB | Kimi K3, GLM-5.3, DeepSeek V4 Pro, Qwen3.8, MiniMax M3 |
| **OVHcloud AI Endpoints** | 🇫🇷 | „Zero data retention", kein Training auf Nutzerdaten | Llama 3.3 70B, Mixtral, DeepSeek-R1, Whisper |
| **Scaleway Generative APIs** | 🇫🇷 | FR-Rechenzentren, ISO 27001/17/18, SOC 2 | Llama 3, Mistral, Mixtral |
| **Nebius AI Studio** | 🇳🇱 | EU-Hosting wählbar (Standort pro Modell ausgewiesen) | Llama, Mistral, Qwen, Nemo |

> *DPA-Detailtexte von OVHcloud und Scaleway konnten nicht final verifiziert werden — vor
> Vertragsschluss die jeweilige Auftragsverarbeitungs-Vorlage prüfen.*

**Anbieter mit US-Konzernsitz und EU-Region (Rechtsraum beachten — siehe §3):**

| Anbieter | EU-Mechanismus | Hinweis |
|---|---|---|
| **Azure OpenAI** | „EU Data Zone" + „EU Data Boundary" | unterliegt als US-Konzern weiter US-Recht |
| **AWS Bedrock** | EU-Regionen Frankfurt/Irland | dito |
| **AWS European Sovereign Cloud** | **GA seit Jan 2026**, erste Region Brandenburg, separat EU-betrieben | Bedrock dort **nur Amazon-Nova-Modelle** zum Start |

Die wichtigste Neuerung Mitte 2026 ist die **AWS European Sovereign Cloud** (EU-betriebene, separate
Partition) — die Modellauswahl ist dort aber noch dünn.

## 3. Datenresidenz: worauf es rechtlich ankommt

Ein Punkt wird oft übersehen — und er ist entscheidend, wenn eure Compliance echte Datenresidenz in
der EU verlangt.

- Eine **EU-Region** allein sagt nichts darüber, welchem **Rechtsraum** ein Anbieter unterliegt. Der
  **US CLOUD Act** (2018) etwa erlaubt US-Behörden, von US-ansässigen Anbietern Daten zu verlangen —
  unabhängig vom Serverstandort. Eine Frankfurt-Region eines US-Konzerns liegt physisch in der EU,
  der Anbieter unterliegt aber weiter US-Recht. Das ist kein Werturteil, sondern ein Faktor, den eine
  saubere Datenresidenz-Strategie einkalkuliert. ([AWS zum CLOUD Act](https://aws.amazon.com/compliance/cloud-act/))
- Das **EU-US Data Privacy Framework** ist Mitte 2026 in Kraft, aber **vor dem EuGH angefochten**
  (Verfahren C-703/25 P, noch anhängig). Wer auf maximale Planungssicherheit setzt, hält die
  Verarbeitung gern von vornherein in der EU. `[Status offen]`
- **DSGVO Art. 44 ff. + Schrems II (2020):** Datenverarbeitung außerhalb der EU braucht eine
  Rechtsgrundlage (Angemessenheitsbeschluss oder SCC + Transfer Impact Assessment).
- **Verschlüsselung ersetzt die Architektur nicht:** LLM-Inferenz braucht den **Klartext** zur
  Verarbeitung — die Datenresidenz wird also über die Architektur entschieden, nicht über ein
  nachträgliches Add-on.

> **Wichtig zur Abgrenzung:** Der **EU AI Act** regelt Risiko und Transparenz — **nicht** die
> Datenresidenz. Wo eure Daten verarbeitet werden müssen, ergibt sich aus der **DSGVO**.
> (Zum AI Act: unser [EU-AI-Act-Leitfaden](https://github.com/azena-ai/eu-ai-act-mittelstand).)

## 4. Europäische Souveränitäts-Landschaft (Mitte 2026)

- **Aleph Alpha (Heidelberg)** hat sich 2024 auf die Enterprise-Plattform **PhariaAI** verlagert; im
  **April 2026** wurde die Fusion mit dem kanadischen **Cohere** angekündigt (Abschluss vorbehaltlich
  Regulierung).
- **Deutsche Telekom + NVIDIA** bauen eine „Industrial AI Cloud" (AI-Factory München, Q1 2026), **SAP**
  liefert den App-Layer. `[teils sekundär]`
- **Schwarz Digits (StackIT) + SAP** bieten souveräne DE-Cloud-Infrastruktur.
- **EU „InvestAI"** (Feb 2025): 20 Mrd € für mehrere KI-Gigafactories auf EU-Boden.

Wer **heute** mit Datenresidenz in der EU bauen will, greift zu offenen Gewichten oder einem
EU-Anbieter (§§1–2) — die Infrastruktur-Ankündigungen reifen parallel.

---

## Entscheidungs-Framework

| Euer Bedarf | Empfehlung |
|---|---|
| **Maximale Datenkontrolle, Verarbeitung im eigenen Haus** | Offene Apache-2.0/MIT-Gewichte **selbst hosten** (Mistral, Teuken, EuroLLM, Qwen, DeepSeek). |
| **Managed, mit Datenresidenz in der EU** | In der EU ansässiger Anbieter: **Mistral La Plateforme, IONOS, OVHcloud, Scaleway**. |
| **Bereits in Azure/AWS** | Gut möglich — geltende Rechtslage (DPF-Status, Rechtsraum) im Transfer Impact Assessment dokumentieren. |
| **Erst verstehen, was geht** | Klein anfangen mit einem self-hosted 7–24B-Modell (Ministral 3, Teuken-7B) auf einer EU-GPU-Instanz. |

## Quellen (Auswahl)

- Mistral-Lizenzen & La Plateforme: <https://mistral.ai/news/mistral-3> · <https://legal.mistral.ai>
- Llama-4-Lizenz (EU-Klausel): <https://github.com/meta-llama/llama-models/blob/main/models/llama4/LICENSE>
- DeepSeek-R1 (MIT): <https://huggingface.co/deepseek-ai/DeepSeek-R1>
- Qwen3 (Apache 2.0): <https://huggingface.co/Qwen/Qwen3-235B-A22B>
- Teuken / OpenGPT-X: <https://opengpt-x.de> · EuroLLM: <https://huggingface.co/utter-project/EuroLLM-22B>
- US CLOUD Act: <https://aws.amazon.com/compliance/cloud-act/>
- DPF-Verfahren (EuGH C-703/25 P): EUR-Lex CELEX 62025CN0703
- AWS European Sovereign Cloud: <https://aws.amazon.com/europe/sovereign-cloud/>

> **Methodik:** Fakten über mehrere Quellen erhoben und die riskanten Aussagen (Lizenzen, EU-Klauseln,
> Rechtslage) gegen Primärquellen gegengeprüft. Als `[offen]` markierte Punkte sind bewusst nicht als
> Gewissheit dargestellt. Modellversionen, die nur auf Aggregator-Seiten kursierten, wurden **nicht**
> übernommen.

**Korrekturen willkommen** — Issue oder PR mit Quellenangabe.

---

<sub>Gepflegt von <a href="https://azena.ai"><b>azena</b></a> · maßgefertigte, EU-souveräne KI für den
deutschen Mittelstand · Stuttgart · Kayra Labs GmbH i. G. · Kein Rechts- oder Steuerrat.</sub>
