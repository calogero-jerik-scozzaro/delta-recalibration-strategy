# Paired Models’ Perplexity Optimization for Categorization on Unbalanced Data

This repository contains code and resources to reproduce the experiments described in our work on **Paired Models’ Perplexity Optimization** for categorization tasks under class imbalance.

There are two ways to run the experiments:

1. **(Optional)** Recompute perplexities from scratch using the original datasets.  
2. **Use the pre-computed perplexities** already included in this repository.  

---

## Quick Start

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

### 2. Create the environment
```bash
python3 -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Run experiments
- **AD experiments:**  
  ```bash
  jupyter notebook delta_recalibration_ad.ipynb
  ```
- **Guardian experiments:**  
  ```bash
  jupyter notebook delta_recalibration_guardian.ipynb
  ```

---

## 1. Recomputing perplexities (optional)

### Alzheimer’s Detection (AD) experiments
- Download the datasets:
  - [1] **ADReSS** (Luz et al., 2020)  
  - [2] **ADReSSo** (Luz et al., 2021)  
- Run preprocessing and perplexity calculation using the code from [PEARL](https://github.com/matteodelsanto/PEARL).  
- Validation sets for each fold are provided in the `adress` and `adresso` folders as `labels_fold_i.csv`.  

### Authorship Attribution (Guardian dataset)
- Download the Guardian dataset from [3] (Stamatatos, 2013).  
- Place it inside the `Guardian/` folder.  
- Run the provided notebook `preprocess_guardian.ipynb`.  
  This will generate the dataset in the format required by [PEARL](https://github.com/matteodelsanto/PEARL) for perplexity computation.  

---

## 2. Using provided perplexities

If you do not wish to recompute perplexities, you can directly use the **pre-computed perplexity values** included in this repository.  
These were obtained following the procedure described above.

- For the AD experiments: run `delta_recalibration_ad.ipynb`.  
- For the authorship attribution experiments: run `delta_recalibration_guardian.ipynb`.  

---

## References

[1] Luz, Saturnino, Fasih Haider, Sofia de la Fuente, Davida Fromm, and Brian MacWhinney. 2020. Alzheimer’s dementia recognition through spontaneous speech: The adress challenge. In Interspeech 2020, pages 2172–2176

[2] Luz, Saturnino, Fasih Haider, Sofia de la Fuente Garcia, Davida Fromm, and Brian MacWhinney. 2021. Alzheimer’s dementia recognition through spontaneous speech.

[3] Stamatatos, Ph D et al. 2013. On the robustness of authorship attribution based on character n-gram features. Journal of Law and Policy, 21(2):7.  
