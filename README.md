# خَلَف | KHALAF-MUB-001-4B

**A research prototype for one documented colloquial speech variety from Al-Mubarraz city, Al-Ahsa Governorate, Saudi Arabia → Modern Standard Arabic (MSA).**

KHALAF (خَلَف) is an Arabic dialect-to-MSA language-model prototype developed as part of the broader **DAAD (ضاد)** Arabic-dialect web-app initiative. *DAAD is the platform; KHALAF is the language model.*

## Overview

- **Variety:** One documented form of colloquial speech associated with **Al-Mubarraz city in Al-Ahsa Governorate, Saudi Arabia** (MUB_001), within the wider Hasawi dialect continuum. The label **Al-Mubarraz colloquial Arabic (العامية المبرزية)** is a practical, project-specific designation, **not** an assertion of a uniform or exclusive city-wide dialect.
- **Task:** Convert dialectal text into Modern Standard Arabic while attempting to preserve meaning, speaker perspective, negation, and gender/number distinctions where context allows.
- **Linguistic focus:** Everyday speech style, sentence structures, phrasing, morphology, and speaker/addressee forms—not only a list of distinctive vocabulary.
- **Base model:** Qwen3-4B-Instruct-2507.
- **Adaptation:** QLoRA fine-tuning; approximately 33 million trainable parameters, three epochs.
- **Training pairs:** 2,500 total (1,000 initial records plus 1,500 synthetic/expanded records with varying levels of human review).
- **Lexicon:** 112 curated entries; 174 surface forms indexed in an experimental linguistic-engine evaluation.
- **Status:** **Research prototype — not independently validated for production.**

### Important clarification about the data
The dataset was **developed with human linguistic input and human review**, including manually authored/edited sentences, AI-assisted proposals reviewed and accepted by the project contributor, and synthetic expansions that received **varying levels of review**. It was **not** entirely written by humans or individually verified by independent reviewers. Linguistic, translation, and annotation errors may remain; this is **not** a fully validated gold-standard corpus.

## Reported experiments

An exploratory, repeatedly inspected **10-item diagnostic set** produced these reported scores:

| System | chrF++ | BLEU |
| --- | ---: | ---: |
| Qwen base (comparison) | 35.71 | 12.17 |
| KHALAF fine-tuned | 64.98 | 52.11 |

**Do not interpret these scores as accuracy or generalization.** The sample was very small, repeatedly inspected, and is **not an independent held-out benchmark**. Qualitative testing also identified mistranslations, gender/number errors, and occasional non-Arabic artifacts.

An automated rule-based audit of a separate experimental 22-input comparison reported the following *review-note flags*, not translation-quality accuracy:

| Variant | Review-note flags | Explicit conflict flags |
| --- | ---: | ---: |
| Qwen original | 16 | 0 |
| Qwen + engine | 6 | 0 |
| KHALAF original | 12 | 2 |
| KHALAF + engine | 10 | 3 |

These numbers are diagnostic only. Some generation settings in the earlier comparison were not yet standardized; no superiority claim follows from this table.

## Repository contents

- [Colab inference notebook](notebooks/KHALAF_MUB_001_4B_Inference.ipynb) — clean inference-only notebook; **does not retrain the model**.
- [Model card](MODEL_CARD.md) — intended use, evaluation limitations, training provenance.
- [Dataset card](DATASET_CARD.md) — data composition and review limitations.
- [Reproducibility](docs/REPRODUCIBILITY.md) — local Drive artifact layout and environment guidance.
- [Publication checklist](docs/PUBLICATION_CHECKLIST.md) — what must be checked before releasing dataset or weights.

## Using the trained adapter

The trained QLoRA adapter was stored in the researcher's Google Drive at:

`DaadUnderstand/MUB_001_Qwen3_4B_v04/final_adapter/`

The linked notebook mounts your Drive and loads that existing adapter with 4-bit quantization. A **CUDA GPU** is required for that notebook's inference path; its CPU-only mode checks files and exits cleanly without generating text. The adapter is **not included in this GitHub repository**. This README does not claim that weights are already publicly downloadable.

## Ethics and limitations

Speech patterns vary among families, neighborhoods, generations, and speakers within **Al-Mubarraz**, and across **Al-Ahsa**. The label **العامية المبرزية** identifies the particular style documented by this project; it does **not** claim to represent every resident, exhaust the city's varieties, or define uniquely Al-Mubarraz-only vocabulary. The dataset emphasizes natural **style and constructions** rather than lexical exclusivity. This prototype does not represent all Hasawi Arabic. Outputs must be reviewed by a competent speaker, particularly where social context, gender, number, or word meaning is ambiguous. It is not suitable for high-stakes uses.

## Publication and licensing

**No open-source or dataset license has been selected yet.** Do not assume permission to redistribute the training data, upstream-derived materials, or model weights. Verify all relevant source and base-model licenses before releasing them on Hugging Face or Zenodo. A public code release may be licensed separately once those checks are complete.

## Project identity

- **DAAD | ضاد:** Arabic dialect intelligence web platform (in development).
- **KHALAF | خَلَف:** language model; named for the continuity of linguistic heritage across generations.
- **This version:** `KHALAF-MUB-001-4B`, exploratory v0.4.

**Project maintainer:** [@yaass24](https://github.com/yaass24).
