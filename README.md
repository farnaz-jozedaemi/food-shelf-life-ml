# Food Shelf-Life Acceptability Prediction

This project applies machine learning to classify food samples as acceptable or rejected using physicochemical, microbial, sensory, storage-condition, and volatile-compound features.

Due to confidentiality considerations, the original product names and dataset identifiers have been anonymized. The methodology and results are presented for educational and portfolio purposes.

## Files

### 01_random_validation_food_shelflife_github_ready.ipynb
Baseline model benchmarking using random grouped validation. Triplicates from the same Day–Temperature condition are kept together using `Group_ID` to reduce data leakage.

### 02_time_aware_validation_food_shelflife_github_ready.ipynb
Rolling time-aware validation where models are trained on earlier storage days and validated on future days. This notebook provides a more realistic evaluation of shelf-life prediction performance.

---

## Methodological Notes

- Acceptability was defined using microbial thresholds based on Total Plate Count (TPC) and Lactic Acid Bacteria (LAB). Therefore, models were evaluated both with and without microbial variables.
- Random validation is used as a baseline, while time-aware validation provides a more realistic assessment because it respects the temporal structure of shelf-life data.
- PCA and clustering are exploratory analyses. Their scalers are fit on the full dataset for visualization purposes only. Supervised models use scaling within the training and validation process.
- The dataset is relatively small and includes triplicate measurements. Results should therefore be considered exploratory and validated on independent datasets before deployment.

---

### Main Findings

- Random validation produced very high performance but tended to overestimate model generalization.
- Time-aware validation provided a more realistic estimate of future prediction performance.
- Multiple models achieved strong predictive performance, including Logistic Regression, Random Forest, Gradient Boosting, Ridge Classifier, and XGBoost, depending on the validation strategy used.
- Simpler linear models generally showed more stable behavior under time-aware validation.
- Comparable performance with and without microbial variables suggests that physicochemical, sensory, and volatile measurements also contain meaningful spoilage information.arable performance with and without microbial variables suggests that physicochemical, sensory, and volatile measurements also contain meaningful spoilage information.

---

## Future Work

- Validate the models using independent external datasets.
- Quantify prediction uncertainty using confidence intervals and repeated validation.
- Develop hybrid approaches combining machine learning and mechanistic shelf-life models.
