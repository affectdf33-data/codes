# AffectDF: The Most Comprehensive Benchmark for Speech Deepfake Detection against Emotionally Expressive Attacks

This repository contains score files and inference outputs used for evaluating speech deepfake detection systems on AffectDF and related benchmark datasets.

The repository includes:

* score files from SDD models trained on AffectDF and evaluated across multiple datasets,
* inference outputs from large audio-language model (LALM)-based detectors,
* repeated inference runs where applicable.

This repository is intended to support reproducibility and analysis for AffectDF-related experiments.

---

## Repository Structure

```text
codes/
├── AffectDF_Trained_scores/
│   ├── AASIST/
│   ├── ProSDD/
│   ├── RawNet2/
│   ├── XLSR-Mamba/
│   └── XLSR-SLS/
│
├── LALM_Inference_Scores/
│   ├── Qwen2.5-Omni/
│   ├── Qwen3-Omni/
│   └── Voxtral/
│
└── README.md
```

---

## AffectDF-Trained Model Scores

The `AffectDF_Trained_scores/` directory contains score files from conventional and SSL-based SDD models trained on AffectDF.

The included models are:

* `RawNet2`
* `AASIST`
* `XLSR-SLS`
* `XLSR-Mamba`
* `ProSDD`

Although these models are trained on AffectDF, their score files include evaluation on multiple datasets, including conventional and emotional speech deepfake benchmarks. Each model folder contains dataset-specific score files used to compute EER and cross-domain evaluation results.

Example structure:

```text
AffectDF_Trained_scores/
├── AASIST/
│   ├── ASVspoof2019.txt
│   ├── ASVspoof2021.txt
│   ├── ASVspoof5.txt
│   ├── AffectDF.txt
│   ├── EmoFake.txt
│   └── EmoSpoofTTS.txt
```

---

## LALM Inference Scores

The `LALM_Inference_Scores/` directory contains prompt-based inference outputs from large audio-language models evaluated for speech deepfake detection.

The included models are:

* `Qwen2.5-Omni`
* `Qwen3-Omni`
* `Voxtral`

Each model folder is organized by evaluation dataset. Multiple `run_*.txt` files are provided when repeated inference runs are available.

Example structure:

```text
LALM_Inference_Scores/
├── Qwen2.5-Omni/
│   ├── ASVspoof5/
│   │   ├── run_1.txt
│   │   ├── run_2.txt
│   │   └── run_3.txt
│   ├── ASVspoof_2019/
│   ├── AffectDF/
│   ├── EmoFake/
│   └── EmoSpoofTTS/
│
├── Qwen3-Omni/
└── Voxtral/
```

Each `run_*.txt` file corresponds to one inference run. The scores reported in the paper are averaged over the three runs.

---

## Model Checkpoints

The trained AffectDF model checkpoints are not stored directly in this repository due to file-size constraints. They are provided separately through external storage.

Link: https://drive.google.com/drive/folders/17Fcw8OvFOtdyv0u_CtKEVR_u8LoD5NiR?usp=drive_link

Available checkpoints include:

```text
AASIST_AffectDF_T.pth
ProSDD_AffectDF_T.pth
RawNet2_AffectDF_T.pth
XLSR-Mamba_AffectDF_T.pth
XLSR-SLS_AffectDF_T.pth
```

These checkpoints correspond to the models listed under `AffectDF_Trained_scores/`.

---

## Intended Use

This repository is intended for research and reproducibility in speech deepfake detection, especially under emotionally expressive spoofing conditions. The files are provided for analysis, benchmarking, and comparison of SDD systems. The outputs and checkpoints should not be used for impersonation, deception, biometric spoofing, or other harmful applications.
