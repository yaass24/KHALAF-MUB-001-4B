# KHALAF-MUB-001-4B — Model Card

## Model identity
- **Arabic name:** خَلَف
- **Model ID:** KHALAF-MUB-001-4B
- **Version:** exploratory v0.4
- **Language:** Arabic
- **Variety:** One documented colloquial speech variety from **Al-Mubarraz city, Al-Ahsa Governorate, Saudi Arabia** (MUB_001); locally categorized in this project as **العامية المبرزية** within the wider Hasawi continuum. This is **not** a representative sample of all Al-Mubarraz speakers or a claim of unique lexical features.
- **Intended task:** dialect-to-MSA text conversion
- **Parent project:** DAAD (ضاد), planned web application
- **Base:** Qwen3-4B-Instruct-2507, pinned to revision `cdbee75f17c01a7cc42f958dc650907174af0554`
- **Adaptation:** QLoRA, 4-bit NF4 with double quantization

## Training summary
- Approximately **2,500 pairs**, three training epochs, effective batch size 16.
- Reported trainable adapter parameters: **33,030,144** of **4,055,498,240** (~0.81%).
- Saved trained adapter location (owner's Drive): `DaadUnderstand/MUB_001_Qwen3_4B_v04/final_adapter/`.
- Reported training completion: 471/471 steps, exit code 0; summary train loss ~0.3105. Training loss is **not** a translation-quality metric.
- No publicly hosted adapter URL is asserted.

## Data provenance
The corpus includes 1,000 initial pairs (some independently authored, others AI-proposed and human-reviewed/accepted or edited), together with 1,500 synthetic/expanded pairs receiving **varying levels of human review**. The linguistic focus is **speech style, phrasing, constructions, and morphology**, not only region-associated vocabulary. Human input and review were part of dataset development, but **not every example was human-authored or independently checked**. Errors in form, meaning, translation, or annotation may remain; the 2,500 pairs are **not** a fully verified gold-standard dataset.

## Exploratory evaluation
Reported 10-item repeatedly inspected diagnostic: base Qwen chrF++ 35.71 / BLEU 12.17; adapted KHALAF chrF++ 64.98 / BLEU 52.11. This diagnostic is too small and repeatedly inspected to establish generalization, accuracy or model superiority. Qualitative tests identified mistranslations, agreement errors and occasional other-script artifacts.

A rule-based linguistic audit over 22 test inputs returned 12 review-note flags for KHALAF without the experimental engine and 10 with it; explicit-conflict flags were 2 and 3 respectively. These **flags are not an accuracy score**. The engine comparison also had earlier generation configuration inconsistencies.

## Intended use
Language technology research, documentation of local linguistic variation, and human-reviewed exploratory dialect-to-MSA conversion.

## Out of scope
Production translation, unsupervised linguistic judgments, automatic claims about all Hasawi dialect speakers, legal/medical/financial decisions, and use requiring high factual or grammatical reliability.

## Known limitations
- One contributor-centered speech variety from Al-Mubarraz, in Al-Ahsa Governorate; limited speaker, neighborhood, and generation coverage. The project label does not imply uniform use across the city.
- Meaning varies by context, neighborhood, and morphology.
- Feminine/masculine and singular/plural markers may be confused.
- Lexicon hints can lead to overcorrection or literal substitutions.
- No independent held-out test suite with full speaker-diverse annotation has yet been reported.
- GPU required by the provided 4-bit inference notebook.

## Redistribution
No redistribution permission is implied. Check base-model license, dataset provenance and the rights to all included sources before publishing adapter weights or the corpus. No license has been assigned to this repository yet.
