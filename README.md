# CatBoost Click‑Through Prediction From ADM HDS Notebook

This repository contains the Jupyter notebook **`catboost_hds.ipynb`**, which demonstrates how to build a gradient‑boosted decision‑tree model with [CatBoost](https://catboost.ai/) to predict click‑through outcomes using ADM historical dataset.

The notebook walks through every stage of the typical machine‑learning workflow—data ingestion, cleaning, feature engineering, model training, evaluation, and explainability—while showcasing advanced CatBoost capabilities such as:

* Automatic handling of **categorical features** without manual encoding
* Built‑in **text processing** via custom tokenizers
* Built‑in evaluation metrics (Logloss, AUC) and visualisation utilities
* Efficient SHAP value computation for **model interpretability**

---

## Folder structure

```
.
├── catboost_hds.ipynb   # Main notebook
├── Web_ClickThrough.zip # Raw dataset 
└── README.md            # You are here 🎉
```

---

## Dataset

The notebook expects a compressed file called **`Web_ClickThrough.zip`** containing the **Click‑Through & Decision Outcomes** export produced by the Pega Customer Decision Hub (or a structurally similar table).
Each row captures:

| Column Group            | Examples                                      | Notes                         |
| ----------------------- | --------------------------------------------- | ----------------------------- |
| Interaction identifiers | `Decision_InteractionID`, `Context_Treatment` | Used to remove duplicates     |
| Contextual features     | `channel`, `language`, `country`              | Categorical                   |
| Numerical metrics       | `propensity`, `score`, `timeOnPage`           | Numeric                       |
| Textual payloads        | `Meta_keywords`, `Search_terms`               | Parsed with a comma tokenizer |

Feel free to swap in your own dataset—just ensure the **target column** is named **`Decision_Outcome`** (binary: *Clicked* = 1, *No‑click* = 0).

## Examples

Decision tree visualization.

<img width="757" alt="tree" src="https://github.com/user-attachments/assets/501c85a0-4a80-4687-a435-b4c1bb4f4650" />

Feature analysis.

<img width="719" alt="feature" src="https://github.com/user-attachments/assets/990dbf4d-81e8-42e0-a67b-9e50679554f4" />

Decision explanaition.

![explain](https://github.com/user-attachments/assets/d99ae8eb-cfc0-47c8-9d4d-d5582cad53b4)



---

## References

* Prokhorenkova L. et al. (2018) *CatBoost: unbiased boosting with categorical features*. NeurIPS.
* Lundberg S., Lee S.‑I. (2017) *A Unified Approach to Interpreting Model Predictions* (SHAP).

---

## License

This notebook is released under the MIT License.
The **sample data** is provided for demonstration purposes only; verify licensing before using it in production.

Enjoy and happy boosting! 🚀
