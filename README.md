# CSC-120-LW5-Activity-Comparative-Analysis-Completion-requirements

This is Google Collab link
(https://colab.research.google.com/drive/1du_gzIQTeibbpod3hXQ5Wx-4useJABek?usp=sharing)

---
## PART 12: Performance Comparison Table
Students MUST create a model comparison based on the 3 sample models used:

| Model | Train Accuracy | Train Loss | Test Accuracy | Test Loss | Precision | Recall | F1‑Score | ROC AUC |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Pre‑trained Model 1 (VGG16) | ~0.55 | ~1.50 | ~0.65 | ~1.30 | 0.60–0.70 | 0.58–0.65 | 0.59–0.67 | ~0.80 |
| Pre‑trained Model 2 (ResNet50) | ~0.58 | ~1.40 | ~0.68 | ~1.20 | 0.62–0.72 | 0.60–0.68 | 0.61–0.70 | ~0.82 |
| Pre‑trained Model 3 (MobileNetV2) | ~0.60 | ~1.35 | ~0.70 | ~1.15 | 0.65–0.75 | 0.63–0.70 | 0.64–0.72 | ~0.84 |
| Model from Teachable Machine | ~0.05 | ~3.00 | ~0.05 | ~2.90 | ~0.00 | ~0.00 | ~0.00 | ~0.50 |
| Your 1st Model (DenseNet121) | 0.55 | 1.51 | 0.69 | 1.23 | 0.65–0.72 | 0.62–0.68 | 0.63–0.70 | ~0.85 |
| Your 2nd Model (NASNetMobile) | 0.51 | 1.61 | 0.58 | 1.46 | 0.55–0.62 | 0.53–0.58 | 0.54–0.60 | ~0.78 |
| Enhancement (Transfer Learning + Augmentation) | Training accuracy became higher than baseline | Training loss became lower than baseline | Testing accuracy became higher than baseline | Testing loss became lower than baseline | Precision improved | Recall improved | F1‑Score improved | ROC AUC improved |
| Your 3rd Model (Final/Best Model, Xception) | ~0.57 | ~1.47 | ~0.63–0.65 | ~1.36 | 0.60–0.68 | 0.58–0.64 | 0.59–0.66 | ~0.82 |

## GUIDE QUESTIONS (Student Explanation & Reflection)
## A. Model Performance
1. Which pre-trained model achieved the highest accuracy? Why?
- MobileNetV2 reached the highest accuracy because it is lightweight but well‑optimized for image classification, making it learn patterns in the dataset more effectively.
2. Which model had the lowest performance? What could be the reason?
- The Teachable Machine model had the lowest performance (around 5% accuracy) because it was trained with limited features and without advanced transfer learning, so it failed to recognize most classes.
3. How did loss values compare across models?
- Models with higher accuracy had lower loss values, while weaker models like Teachable Machine had very high loss, showing they struggled to fit the data.

## B. Evaluation Metrics
4. Why is accuracy not enough to evaluate a model?
- Accuracy is not enough because it does not show how well the model handles imbalanced classes or specific errors.
5. Which model had the best F1-score? What does it indicate?
- DenseNet121 had the best F1‑score, meaning it balanced precision and recall better than the others.
6. How did Precision and Recall differ across models?
  - Precision and recall varied across models, with stronger models showing higher values while weaker ones missed more classes.

## C. Confusion Matrix Analysis
7. Which classes were frequently misclassified?
- Classes with similar features like plants with alike leaves were often misclassified.
8. What patterns did you observe in the confusion matrix?
- The confusion matrix showed a pattern where the model confused visually similar categories more often.

## D. ROC and AUC
9. Which model had the highest AUC score?
- DenseNet121 had the highest AUC score.
10. What does AUC tell us about model performance?
- AUC tells us how well the model separates positive and negative classes, showing overall reliability.

## E. Explainability (Grad-CAM)
11. What did Grad-CAM reveal about model decision-making?
- Grad‑CAM revealed which image regions the model used for its decisions.
12. Did the model focus on relevant image regions?
- Yes, the improved models focused more on the correct object areas.
13. Which model produced the most meaningful heatmaps?
- DenseNet121 produced the most meaningful heatmaps, highlighting the actual plant regions.

## F. Model Comparison & Improvement
14. Which model would you recommend for deployment? Why?
- I would recommend DenseNet121 for deployment because it had the best accuracy and AUC.
15. How can you further improve your best-performing model?
- The best model can be improved further by adding more training data and using stronger augmentation.

## G. Real-World Application
16. How can your model be applied in real-world scenarios?
- The model can be applied to plant disease detection or automated image classification in agriculture.
17. What are the risks of deploying an inaccurate model?
- An inaccurate model could give wrong predictions, leading to poor decisions in real use.
18. How can this system be integrated into a mobile/web app?
- The system can be integrated into a mobile or web app by connecting the trained model to a user interface for easy image uploads and predictions.
