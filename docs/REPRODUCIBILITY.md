# Reproducibility and inference

## Trained artifacts (private Google Drive)
The completed KHALAF research run is recorded under:

```text
MyDrive/
└── DaadUnderstand/
    └── MUB_001_Qwen3_4B_v04/
        ├── experiment.json
        ├── final_adapter/
        │   ├── adapter_config.json
        │   └── adapter_model.safetensors
        ├── train_qwen.py
        └── debug_log.txt
```

Other training-data and evaluation files may be in the same folder. Paths above document the historical experiment; they are **not public GitHub downloads**.

## Run the notebook
1. In Google Colab, open `notebooks/KHALAF_MUB_001_4B_Inference.ipynb`.
2. Select a **T4 GPU** (or compatible CUDA backend).
3. Mount the Google Drive account containing the completed run.
4. Run the environment checks, dependency installation, and inference cell **in that order**.
5. If a package install caused imports to fail, restart the runtime and rerun the cells.

The inference code keeps the original path and metadata (`meta["base"]`, `meta["revision"]`, `meta["system"]`) rather than guessing a new checkpoint. It loads the base at the pinned revision and then attaches `final_adapter`. It uses greedy decoding with sampling disabled.

## Without a GPU
The notebook checks that saved adapter files are present and prints that inference was skipped. It does **not** raise `SystemExit` and does **not** attempt CPU generation with the 4B model.

## Training details
Training was completed previously using QLoRA with the 2,500-pair dataset. This cleaned publication notebook **does not replicate the historical training process or bundle original data**. Exact training reproducibility would require the original script, verified corpus, compatible environment, and documented training random seeds after redistribution permission is established.

## No hidden benchmark claims
The 10-item repeatedly inspected diagnostic and the 22-input rule-based audit are preliminary. An independent multi-speaker test set and standardized generation comparison remain future work.
