# KHALAF-MUB-001 — Dataset Card (documentation only)

## Scope
A dataset documenting **one colloquial speech variety used in Al-Mubarraz city, Al-Ahsa Governorate, Saudi Arabia**, aligned with Modern Standard Arabic for dialect-to-MSA research. The project calls this variety **العامية المبرزية (Al-Mubarraz colloquial Arabic, MUB_001)** as a **descriptive working label**, not a claim that all Al-Mubarraz residents share one dialect or that its words are unique to the city. **2,500 pairs were used for the reported experiment.**

## Composition
| Component | Count | Review description |
| --- | ---: | --- |
| Initial dataset | 1,000 | Mix of independently translated records, approved AI proposals, and manually edited proposals |
| Synthetic expansions | 1,500 | Generated/expanded examples with variable review depth |
| **Total** | **2,500** | **Not a gold-standard, individually audited corpus** |

The initial 1,000 included **110** independently human-translated pairs, **766** AI proposals reviewed and accepted as-is, and **124** AI proposals edited and approved. A later report on the 1,500 expansions noted **69** corrections and **1,431** collectively accepted records with varying review depth. These are project workflow records, **not independent quality-certification counts**.

**Human involvement and remaining uncertainty:** The dataset was built with direct human linguistic input and review, including manual corrections. It was **not wholly human-written**, and the synthetic portion did **not** receive uniformly documented sentence-by-sentence independent verification. Despite this review, **dialectal, semantic, translation, or annotation errors are possible**.

## Linguistic notes
The scope is **one contributor-centered speech style**, with particular emphasis on **natural phrasing, sentence structures, morphology, and ways of speaking** rather than a glossary of unusual words. Usage may differ between Al-Mubarraz neighborhoods, families, generations, and speakers; features are **not exclusive to the city**, and this dataset cannot represent every variety spoken there. Examples of relevant forms include `استنانيا` (“wait for me”), `استنينيا` (“wait for me”, feminine addressee), `منيا` (“from me”), and `هالحجي` (“this speech”). Annotation must preserve addressee gender and number where expressed.

## Quality and bias
Synthetic content may overrepresent construction patterns or amplify model-generated errors. One contributor/reviewer cannot establish **city-wide or region-wide** linguistic representativeness. Phrase-level ambiguities and source–target inconsistencies require additional independent review before use as a benchmark.

## Privacy, rights and distribution
**Training data are intentionally not committed here.** Check contributor permission, licensing of model-generated and externally sourced materials, personal data and local-speaker consent before any dataset release. A dataset license has not been selected.

## Suggested columns
`id`, `dialect_text`, `msa`, `variety_id`, `source`, `review_status`, `addressee_gender`, `addressee_number`, and other provenance fields where available.
