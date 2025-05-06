# NLP-Shared-Task-8

## Team Members

We were **Team 6**, working on **SemEval-2024 Task 8: Multigenerator, Multidomain, and Multilingual Black-Box Machine-Generated Text Detection**.
The following were the key contributors to this project:

* **Upvandeep Kaur**: [upvandeep.kaur@colorado.edu](mailto:upvandeep.kaur@colorado.edu)
* **Shrestha Acharya**: [shac6361@colorado.edu](mailto:shac6361@colorado.edu)
* **Sagar Swami Rao Kulkarni**: [saku8738@colorado.edu](mailto:saku8738@colorado.edu)

## Task Overview

We participated in **Subtask A - Monolingual Track** of SemEval-2024 Task 8, focusing on **Binary Human-Written vs. Machine-Generated Text Classification**. The objective was to classify whether a given full text was **human-written** or **machine-generated**. We worked with monolingual (English) sources in this subtask.

### Problem Statement

The goal was to determine whether a full text was:

* **Human-written** (Label: 0)
* **Machine-generated** (Label: 1)

This task addressed the growing challenge of distinguishing between human-written and machine-generated content, particularly with the rise of sophisticated AI models like ChatGPT, Davinci, Cohere, and Dolly. Efficient methods for detection were critical to mitigate the risks posed by AI-generated misinformation.

## Approach

Our approach integrated a combination of **traditional machine learning models** and **transformer-based architectures**. We fine-tuned **RoBERTa Base** and **RoBERTa Large** models, implementing extensive **hyperparameter tuning** to optimize the models' performance on the text classification task.

### Models Used:

* **Traditional Models**:

  * Linear SVM
  * Random Forest
  * AdaBoost
  * XGBoost
  * Naïve Bayes

* **Transformer Models**:

  * **RoBERTa Base**
  * **RoBERTa Large**

### Hyperparameter Tuning

In order to achieve optimal model performance, we performed extensive hyperparameter tuning, particularly for the **RoBERTa Base** and **RoBERTa Large** models. The following hyperparameters were adjusted during the tuning process:

* **Batch Size**: We adjusted the batch sizes for optimal performance and to manage memory constraints (e.g., **RoBERTa Base** used batch size of **8**, **RoBERTa Large** used batch size of **16**).
* **Learning Rate**: We fine-tuned the learning rates to balance training speed and model performance, setting them to **1e-4** and **1e-5** for various models.
* **Optimizer**: We tested both **SGD** and **Adam** optimizers, with **Adam** yielding better performance.
* **Early Stopping**: We applied early stopping after **3 epochs** to prevent overfitting and to ensure efficient use of computational resources.
* **Tokenization and Feature Extraction**: We used techniques like **TF-IDF** for traditional models and **BERT tokenizer** for RoBERTa to convert the raw text into numerical features for the models.

### Computational Resources

Training large transformer models like **RoBERTa Base** and **RoBERTa Large** required significant computational resources. Here’s a breakdown of the infrastructure we used for this task:

* **Google Colab Pro**: We utilized the high-performance computing resources available on Google Colab Pro, specifically **A100 GPUs** (with 40GB of memory) for **RoBERTa Large** and **V100 GPUs** (with 20GB of memory) for **RoBERTa Base**.
* **Cloud Resources**: Access to cloud-based GPUs allowed us to fine-tune large models with more flexibility, as local systems did not have sufficient memory and computational power.
* **Memory Constraints**: Given the size of the transformer models, **RoBERTa Large** required substantial memory. We carefully managed batch sizes and implemented early stopping to fit within available memory limits.
* **Training Time**: The fine-tuning process took several hours to days per model, depending on the specific model and batch size used. We used early stopping to optimize runtime and prevent overfitting.

## Results

We evaluated our models using **precision**, **recall**, **accuracy**, and **F1 score**. Below is a summary of the performance of each model on the classification task:

### F1 Scores for Each Model:

| Model             | F1 Score (Human-Written) | F1 Score (Machine-Generated) | Average F1 Score |
| ----------------- | ------------------------ | ---------------------------- | ---------------- |
| **Linear SVM**    | 0.70                     | 0.60                         | 0.65             |
| **Random Forest** | 0.74                     | 0.68                         | 0.71             |
| **AdaBoost**      | 0.61                     | 0.65                         | 0.63             |
| **XGBoost**       | 0.69                     | 0.65                         | 0.67             |
| **Naïve Bayes**   | 0.68                     | 0.64                         | 0.66             |
| **RoBERTa Base**  | 0.85                     | 0.83                         | 0.84             |
| **RoBERTa Large** | 0.89                     | 0.85                         | 0.87             |

### Key Takeaways:

* **RoBERTa Large** outperformed all other models with an impressive **average F1 score of 0.87**.
* **RoBERTa Base** also performed well, achieving an **average F1 score of 0.84**.
* Among traditional models, **Random Forest** showed the highest performance with an **F1 score of 0.71**.

These results clearly demonstrated that transformer-based models, particularly **RoBERTa Large**, provided significant improvements over traditional models for this text classification task.

## Resources

The finetuned model weights for **RoBERTa Base** and **RoBERTa Large** can be found at the following link:
[Download RoBERTa Weights](https://drive.google.com/drive/folders/1JbFDA-2eBpspj6PmfKxm6z3DBIK8-NfK?usp=sharing)

## Acknowledgements

We would like to thank **Prof. James Martin** for his guidance and support, as well as for providing the opportunity to contribute to **SemEval-2024 Task 8**.
