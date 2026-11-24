# خَلَف | KHALAF-MUB-001-4B

**A research prototype for Al-Mubarraz colloquial Arabic → Modern Standard Arabic (MSA).**

KHALAF (خَلَف) is an Arabic dialect-to-MSA language-model prototype developed as part of the broader **DAAD (ضاد)** Arabic-dialect web-app initiative. *DAAD is the platform; KHALAF is the language model.*

## Overview

- **Variety:** Al-Mubarraz colloquial Arabic, a local variety within the Hasawi Arabic dialect continuum (MUB_001).
- **Task:** Convert dialectal text into Modern Standard Arabic while preserving meaning, speaker perspective, negation, and gender/number distinctions where context allows.
- **Base model:** Qwen3-4B-Instruct-2507.
- **Adaptation:** QLoRA fine-tuning; approximately 33 million trainable parameters, three epochs.
- **Training pairs:** 2,500 total (1,000 initial records plus 1,500 synthetic/expanded records with varying levels of human review).
- **Lexicon:** 112 curated entries; 174 surface forms indexed in an experimental linguistic-engine evaluation.
- **Status:** **Research prototype — not independently validated for production.**

### Important clarification about the data
The 2,500 pairs were **not all independently human-translated or individually verified**. The source material combines manually authored/edited entries, AI-assisted proposals accepted by a reviewer, and synthetic expansions receiving different levels of review. This repository does **not** describe them as a fully verified gold-standard corpus.

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

Dialect usage differs across neighborhoods and speakers, even within Al-Ahsa. This prototype represents an initial *Al-Mubarraz-centered* contribution, not all Hasawi Arabic. Outputs must be reviewed by a competent speaker, particularly where social context, gender, number, or word meaning is ambiguous. It is not suitable for high-stakes uses.

## Publication and licensing

**No open-source or dataset license has been selected yet.** Do not assume permission to redistribute the training data, upstream-derived materials, or model weights. Verify all relevant source and base-model licenses before releasing them on Hugging Face or Zenodo. A public code release may be licensed separately once those checks are complete.

## Project identity

- **DAAD | ضاد:** Arabic dialect intelligence web platform (in development).
- **KHALAF | خَلَف:** language model; named for the continuity of linguistic heritage across generations.
- **This version:** `KHALAF-MUB-001-4B`, exploratory v0.4.

**Project maintainer:** [@yaass24](https://github.com/yaass24).
