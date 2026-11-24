# KHALAF-MUB-001 — Dataset Card (documentation only)

## Scope
Al-Mubarraz colloquial Arabic (a local Hasawi variety) aligned with Modern Standard Arabic for dialect-to-MSA model training. **2,500 pairs were used for the reported experiment.**

## Composition
| Component | Count | Review description |
| --- | ---: | --- |
| Initial dataset | 1,000 | Mix of independently translated records, approved AI proposals, and manually edited proposals |
| Synthetic expansions | 1,500 | Generated/expanded examples with variable review depth |
| **Total** | **2,500** | **Not a gold-standard, individually audited corpus** |

The initial 1,000 included **110** independently human-translated pairs, **766** AI proposals accepted as-is, and **124** AI proposals edited and approved. A later report on the 1,500 expansions noted **69** corrections and **1,431** collectively accepted records with varying review depth. These are project records, **not independent quality-certification counts**.

## Linguistic notes
One contributor-centered local variety; dialect features are **not exclusive to Al-Mubarraz**. Examples of relevant forms include `استنانيا` (“wait for me”), `استنينيا` (“wait for me”, feminine addressee), `منيا` (“from me”), and `هالحجي` (“this speech”). Annotation must preserve addressee gender and number where expressed.

## Quality and bias
Synthetic content may overrepresent construction patterns or amplify model-generated errors. One speaker/reviewer cannot establish region-wide linguistic representativeness. Phrase-level ambiguities and source–target inconsistencies require additional independent review before use as a benchmark.

## Privacy, rights and distribution
**Training data are intentionally not committed here.** Check contributor permission, licensing of model-generated and externally sourced materials, personal data and local-speaker consent before any dataset release. A dataset license has not been selected.

## Suggested columns
`id`, `dialect_text`, `msa`, `variety_id`, `source`, `review_status`, `addressee_gender`, `addressee_number`, and other provenance fields where available.
