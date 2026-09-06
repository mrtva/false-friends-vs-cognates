This repository contains the datasets for the paper: ***False Friends or Cognates? A Cross-lingual Semantic Ambiguity Evaluation for Galician, Portuguese and Spanish***.

The paper assesses whether current language models can distinguish **cognates** from **false friends** between: **Galician (GL)**, **Portuguese (PT)** and **Spanish (ES)**. 

## Datasets

Each instance consists of a word pair in two languages, one context sentence per word, and a label indicating whether both target words share the same meaning in context (**cognate**) or not (**false friend**).

| Pair | Cognates | False friends | Word pairs | Sentences |
| ------------- | --------- | -------------- | ----------- | ---------- |
| **ES–PT** | 182 | 182 | 364 | 728 |
| **GL–ES** | 75 | 75 | 150 | 300 |
| **GL–PT** | 95 | 95 | 190 | 380 |
| **Total** | 352 | 352 | 704 | 1,408 |

Each language pair has two subsets:

- Semi-automatic (`auto`): context sentences were extracted from 2024 Wikipedia dumps, and validated by experts.
- Human-authored (`human`): new sentences written by the annotators.

Both subsets were validated by two annotators with a linguistic background (raw agreement 90.43%, pooled Cohen's κ = 0.839; ES–PT: 0.800, GL–ES: 0.809, GL–PT: 0.854). Pairs without consensus were discarded.

False friends are further annotated as **total** (TFF), where the meanings fully diverge, or **partial** (PFF), where at least one sense still overlaps.

| Subset | Pair | COG | TFF | PFF | Total |
| ------ | ------ | --- | --- | --- | ----- |
| Auto | ES–PT | 152 | 66 | 87 | 304 |
| Auto | GL–ES | 50 | 30 | 20 | 100 |
| Auto | GL–PT | 65 | 22 | 43 | 130 |
| Human | ES–PT | 30 | 11 | 19 | 60 |
| Human | GL–ES | 25 | 16 | 9 | 50 |
| Human | GL–PT | 30 | 10 | 20 | 60 |

## Dataset format

Each dataset is a TSV file following the [**WiC structure**](https://arxiv.org/abs/1808.09121), extended with the cross-lingual and semantic-type fields:

| Column | Description |
| --------- | ------------------------------------------------------- |
| `W1` / `W2` | Target words |
| `C1` / `C2` | Context sentences |
| `P1` / `P2` | Position of the target token in each sentence |
| `R` | `1` = same sense (cognate), `0` = different sense (false friend) |
| `PoS` | Part of speech. Combined tags (e.g. `N/A`) indicate categories that differ across the two languages |

Example instances:
This repository contains the datasets for the paper: ***False Friends or Cognates? A Cross-lingual Semantic Ambiguity Evaluation for Galician, Portuguese and Spanish***.

The paper assesses whether current language models can distinguish **cognates** from **false friends** between: **Galician (GL)**, **Portuguese (PT)** and **Spanish (ES)**. 

## Datasets

Each instance consists of a word pair in two languages, one context sentence per word, and a label indicating whether both target words share the same meaning in context (**cognate**) or not (**false friend**).

| Pair | Cognates | False friends | Word pairs | Sentences |
| ------------- | --------- | -------------- | ----------- | ---------- |
| **ES–PT** | 182 | 182 | 364 | 728 |
| **GL–ES** | 75 | 75 | 150 | 300 |
| **GL–PT** | 95 | 95 | 190 | 380 |
| **Total** | 352 | 352 | 704 | 1,408 |

Each language pair has two subsets:

- Semi-automatic (`auto`): context sentences were extracted from 2024 Wikipedia dumps, and validated by experts.
- Human-authored (`human`): new sentences written by the annotators.

Both subsets were validated by two annotators with a linguistic background (raw agreement 90.43%, pooled Cohen's κ = 0.839; ES–PT: 0.800, GL–ES: 0.809, GL–PT: 0.854). Pairs without consensus were discarded.

False friends are further annotated as **total** (TFF), where the meanings fully diverge, or **partial** (PFF), where at least one sense still overlaps.

| Subset | Pair | COG | TFF | PFF | Total |
| ------ | ------ | --- | --- | --- | ----- |
| Auto | ES–PT | 152 | 66 | 87 | 304 |
| Auto | GL–ES | 50 | 30 | 20 | 100 |
| Auto | GL–PT | 65 | 22 | 43 | 130 |
| Human | ES–PT | 30 | 11 | 19 | 60 |
| Human | GL–ES | 25 | 16 | 9 | 50 |
| Human | GL–PT | 30 | 10 | 20 | 60 |

## Dataset format

Each dataset is a TSV file following the [**WiC structure**](https://arxiv.org/abs/1808.09121), extended with the cross-lingual and semantic-type fields:

| Column | Description |
| --------- | ------------------------------------------------------- |
| `W1` / `W2` | Target words |
| `C1` / `C2` | Context sentences |
| `P1` / `P2` | Position of the target token in each sentence |
| `R` | `1` = same sense (cognate), `0` = different sense (false friend) |
| `PoS` | Part of speech. Combined tags (e.g. `N/A`) indicate categories that differ across the two languages |


Example instances:

| W1 | C1 | W2 | C2 | R | POS |
| --- | --- | --- | --- | --- | --- |
| talher | *Deve ser comido apenas com as mãos, jamais com talheres.* | taller | *También tiene un moderno taller de restauración.* | **0** | N |
| voto | *Só se permite un voto por familia.* | voto | *Havia apenas dois votos a favor da proposta.* | **1** | N |

## Citation 
If you use these resources, please cite: [False Friends or Cognates? A Cross-lingual Semantic Ambiguity Evaluation for Galician, Portuguese and Spanish](https://aclanthology.org/2026.acl-long.1818/) (Abuín et al., ACL 2026)


