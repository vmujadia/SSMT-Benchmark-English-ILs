# SSMT-Benchmark-English-ILs

## Speech-to-Speech Machine Translation Benchmark  
### English → Indian Languages (Indic)

**SSMT-Benchmark-English-ILs** is a benchmark dataset and evaluation suite designed for **Speech-to-Speech Machine Translation (SSMT)** research involving **English and low-resource Indian languages (ILs)**.

It provides:

- Gold reference translations
- ASR transcripts
- Evaluation scripts
- Standardized test sets
- Reproducible benchmarking setup

The goal is to enable **fair, consistent, and comparable evaluation** of cascaded or end-to-end speech translation systems for Indic languages.

---

## ✨ Motivation

Most speech translation benchmarks focus on high-resource or European language pairs. Indian languages remain under-represented despite:

- Large speaker populations
- High linguistic diversity
- Limited speech resources
- Frequent disfluencies in spoken data
- Domain variability (education, governance, public services)

This benchmark helps address these gaps by providing **carefully curated evaluation data for English → Indic speech translation**.

It is particularly useful for:

- ASR → MT → TTS pipelines
- End-to-end Speech Translation models
- Low-resource MT research
- Indic language modeling
- Disfluency-aware translation systems

---

## 📂 Repository Structure

```

SSMT-Benchmark-English-ILs/
│
├── asr/                # ASR transcripts or system outputs
├── gold/               # Gold reference translations
├── eval_scripts/       # BLEU / COMET / ChrF evaluation scripts
├── data_stats/         # Dataset statistics and metadata
├── LICENSE
└── README.md

```

### Folder Description

| Folder | Description |
|-------|-------------|
| `gold/` | Human translated references for evaluation |
| `asr/` | Example or placeholder ASR outputs / system hypotheses |
| `eval_scripts/` | Metric computation scripts |
| `data_stats/` | Corpus statistics and metadata |

---

## 🌍 Supported Languages

The benchmark covers **English → multiple Indian languages**, including:

- Hindi (hin)
- Bengali (ben)
- Marathi (mar)
- Tamil (tam)
- Telugu (tel)
- Gujarati (guj)
- Kannada (kan)
- Malayalam (mal)
- (additional languages may be included)

Each language directory contains aligned files:

```

source.en
reference.xx

````

---

## 🚀 Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/vmujadia/SSMT-Benchmark-English-ILs.git
cd SSMT-Benchmark-English-ILs
````

---

### 2. Generate predictions

Run your Speech Translation pipeline:

```
English Speech
   ↓
ASR
   ↓
MT
   ↓
(Optional TTS)
   ↓
Translated text
```

Save predictions in plain text:

```
my_outputs.txt
```

(one sentence per line, aligned with references)

---

### 3. Evaluate

### BLEU (SacréBLEU)

```bash
pip install sacrebleu

sacrebleu gold/reference.hin -i my_outputs.txt -m bleu chrf
```

---

### COMET

```bash
pip install unbabel-comet

comet-score -s gold/source.en -t my_outputs.txt -r gold/reference.hin
```

---

### Using provided script (example)

```bash
python eval_scripts/calc_bleu.py \
  --hyp my_outputs.txt \
  --ref gold/reference.hin
```

---

## 📊 Recommended Metrics

We suggest reporting:

| Metric | Why                                             |
| ------ | ----------------------------------------------- |
| BLEU   | Standard MT metric                              |
| ChrF   | Better for morphologically rich Indic languages |
| COMET  | Neural, semantic quality metric                 |

For speech translation, combining **BLEU + COMET** gives more reliable evaluation.

---

## 🔬 Example Research Use Cases

This benchmark can be used for:

* Cascaded SSMT (ASR→MT→TTS)
* End-to-end Speech Translation
* Disfluency removal before MT
* Low-resource fine-tuning
* Domain adaptation
* Indic multilingual models
* Benchmarking Whisper + MT pipelines
* Indic LLM-based translation

---

## 📚 Citation

If you use this dataset or benchmark, please cite:

**Mujadia et al., 2025 — Language Resources and Evaluation**

> Disfluency processing for cascaded speech translation involving English and Indian languages

### BibTeX

```bibtex
@article{Mujadia2025Disfluency,
  title={Disfluency processing for cascaded speech translation involving English and Indian languages},
  author={Mujadia, Vandan and Mishra, Pruthwik and Sharma, Dipti Misra},
  journal={Language Resources and Evaluation},
  volume={59},
  pages={2653--2686},
  year={2025},
  publisher={Springer}
}
```

Paper link:
[https://link.springer.com/article/10.1007/s10579-025-09818-3](https://link.springer.com/article/10.1007/s10579-025-09818-3)

---

## 🤝 Contributing

Contributions are welcome:

* New languages
* Additional evaluation metrics
* Script improvements
* Data cleaning
* More test sets

Steps:

1. Fork
2. Create branch
3. Commit changes
4. Open PR

---

## ⚠️ Notes

* Ensure predictions are **line-aligned** with references.
* Do not shuffle or modify test set ordering.
* Use UTF-8 encoding.
* Normalize punctuation consistently.

---

## 📜 License

Released under the MIT License.

---

## 👤 Maintainer

Vandan Mujadia
GitHub: [https://github.com/vmujadia](https://github.com/vmujadia)

For questions or collaborations, please open an issue.

---

## ⭐ Acknowledgement

If this benchmark helps your research, please consider starring ⭐ the repository.

Happy benchmarking 🚀
