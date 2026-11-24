# Publication checklist

## Already documented
- [x] Separate **DAAD** (web-app platform) from **KHALAF** (model).
- [x] Identify base model, locale, architecture and adaptation method.
- [x] Record 2,500-pair data provenance without implying universal human verification.
- [x] Describe the model's known weaknesses and evaluation caveats.
- [x] Provide a minimal Colab notebook without raw dataset, tokens, cached outputs, or automatic retraining.
- [x] Keep the saved Google Drive artifact path unchanged.

## Before public release
- [ ] Review GitHub repository **visibility** and choose public/private.
- [ ] Verify rights for each included dataset component; obtain any necessary consent.
- [ ] Confirm upstream model's license and permissions to redistribute its adapter.
- [ ] Select and add a suitable code license; specify a **separate dataset license** if releasing data.
- [ ] Run a secret/privacy scan on any newly added training files.
- [ ] Optionally publish adapter to Hugging Face with full model card and a real verified link.
- [ ] Optionally publish the dataset with its own detailed provenance/license.
- [ ] Run standardized inference and a speaker-diverse independent evaluation; report raw sample counts, confidence intervals where appropriate, and failure modes.
- [ ] Create a GitHub Release and link Zenodo to archive an approved, sanitized version; **a DOI does not imply peer review**.

> Repository is intentionally light: code, documentation, and no weights or full training dataset. Do not represent it as a publicly runnable pretrained model without publishing adapter weights legally.
