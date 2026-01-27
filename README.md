TOPSIS-for-Pretrained-Models
============================

TOPSIS Implementation in Python
-------------------------------

**Course:** UCS654 -- Predictive Analytics using Statistics\
**Assignment:** Assignment-5 (TOPSIS)\
**Author:** Nimish Agrawal\
**Roll Number:** 102483077

* * * * *

📌 About the Project
--------------------

This repository presents an implementation of the **TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution)** method for selecting the **best pre-trained transformer model for text classification**.

TOPSIS is a **multi-criteria decision-making (MCDM)** technique that ranks alternatives based on their distance from an **ideal best** and an **ideal worst** solution.\
Instead of evaluating models using a single metric such as accuracy, this project considers multiple performance and efficiency parameters to make a balanced decision.

* * * * *

🎯 Objective
------------

To identify the **most suitable pre-trained NLP model for text classification** by applying the TOPSIS method on multiple evaluation criteria.

* * * * *

📂 Dataset
----------

-   **Dataset:** IMDb Movie Reviews

-   **Task:** Binary Sentiment Classification (Positive / Negative)

-   **Source:** Hugging Face (`stanfordnlp/imdb`)

-   **Evaluation:** Subset of test data (resource-aware evaluation)

* * * * *

🤖 Models Evaluated
-------------------

The following **five pre-trained transformer models** were evaluated:

-   BERT

-   DistilBERT

-   ALBERT

-   ELECTRA

-   RoBERTa

* * * * *

📐 Evaluation Criteria
----------------------

Each model was evaluated using five criteria:

| Criterion | Description | Nature |
| --- | --- | --- |
| Accuracy | Overall correctness of predictions | Benefit |
| F1-score | Balance between precision and recall | Benefit |
| Precision | Correctness of positive predictions | Benefit |
| Inference Time (ms) | Average prediction time | Cost |
| Model Size (MB) | Storage and memory requirement | Cost |

* * * * *

⚖️ Weights Used in TOPSIS
-------------------------

| Criterion | Weight |
| --- | --- |
| Accuracy | 0.25 |
| F1-score | 0.20 |
| Precision | 0.15 |
| Inference Time | 0.20 |
| Model Size | 0.20 |

The weights were chosen to balance model performance and computational efficiency.
Accuracy was given the highest weight as it reflects overall prediction correctness. F1-score and precision were included to capture the quality and balance of predictions. Inference time and model size were assigned significant weights to account for real-world deployment constraints such as speed and resource usage.
This balanced weighting ensures that the selected model performs well while remaining efficient and practical.
* * * * *

📊 Model Evaluation Results (Decision Matrix)
---------------------------------------------

The evaluated metrics were stored in a decision matrix.

📁 **File:** `data/decision_matrix.csv`

| Model | Accuracy | F1-score | Precision | Inference Time (ms) | Model Size (MB) |
| --- | --- | --- | --- | --- | --- |
| BERT | 0.496667 | 0.025806 | 0.400000 | 519.720859 | 417.647469 |
| DistilBERT | 0.506667 | 0.026316 | 1.000000 | 246.064145 | 255.413094 |
| ALBERT | 0.483333 | 0.645309 | 0.491289 | 550.528887 | 44.575203 |
| ELECTRA | 0.496667 | 0.654462 | 0.498258 | 494.411416 | 417.647469 |
| RoBERTa | 0.490000 | 0.231156 | 0.469388 | 495.341160 | 475.491219 |

* * * * *

📈 Graphical Analysis
---------------------

Five graphs were generated to compare **all five models** across each evaluation parameter:

1.  Accuracy Comparison

2.  F1-score Comparison

3.  Precision Comparison

4.  Inference Time Comparison

5.  Model Size Comparison

📁 **Graphs Location:** `Graphs/`

These graphs provide a visual comparison of model performance and efficiency.

* * * * *

🧮 TOPSIS Final Ranking
-----------------------

After applying the TOPSIS method, the final ranking was obtained.

📁 **File:** `topsis_result.csv`

### Final Result Table

| Model | TOPSIS Score | Rank |
| --- | --- | --- |
| ALBERT | 0.678593 | 1 |
| ELECTRA | 0.532406 | 2 |
| DistilBERT | 0.420277 | 3 |
| RoBERTa | 0.221835 | 4 |
| BERT | 0.079984 | 5 |

* * * * *

![Result Graph](image.png)

🏆 Conclusion
-------------

The TOPSIS analysis identified **ALBERT** as the most suitable pre-trained model for text classification.\
Although several models achieved similar accuracy values, ALBERT demonstrated the **best balance between performance and efficiency**, largely due to its strong F1-score and significantly smaller model size.

This project highlights the importance of **multi-criteria evaluation** and demonstrates that accuracy alone is insufficient for model selection.