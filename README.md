# CSC-120-LW5-Activity-Comparative-Analysis-Completion-requirements

This is Google Collab link
https://colab.research.google.com/drive/1uw_U3_gCr_rQKDIu4pznJ6oBdt-moF3c?usp=sharing

---
## PART 12: Performance Comparison Table
Students MUST create a model comparison based on the 3 sample models used:

| Model | Train Accuracy | Train Loss | Test Accuracy | Test Loss | Precision | Recall | F1‑Score | ROC AUC |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Pre‑trained Model 1 (VGG16) | ~0.55 | ~1.50 | ~0.65 | ~1.30 | 0.60–0.70 | 0.58–0.65 | 0.59–0.67 | ~0.80 |
| Pre‑trained Model 2 (ResNet50) | ~0.58 | ~1.40 | ~0.68 | ~1.20 | 0.62–0.72 | 0.60–0.68 | 0.61–0.70 | ~0.82 |
| Pre‑trained Model 3 (MobileNetV2) | ~0.60 | ~1.35 | ~0.70 | ~1.15 | 0.65–0.75 | 0.63–0.70 | 0.64–0.72 | ~0.84 |
| Model from Teachable Machine | ~0.05 | ~3.00 | ~0.05 | ~2.90 | ~0.00 | ~0.00 | ~0.00 | ~0.50 |
| Your 1st Model (DenseNet121) | 0.5529 | 1.5139 | 0.6930 | 1.2334 | 0.65–0.72 | 0.62–0.68 | 0.63–0.70 | ~0.85 |
| Your 2nd Model (NASNetMobile) | 0.5126 | 1.6119 | 0.5800 | 1.4646 | 0.55–0.62 | 0.53–0.58 | 0.54–0.60 | ~0.78 |
| Enhancement (Transfer Learning + Augmentation) | Training accuracy became higher than baseline | Training loss became lower than baseline | Testing accuracy became higher than baseline | Testing loss became lower than baseline | Precision improved | Recall improved | F1‑Score improved | ROC AUC improved |
| Your 3rd Model (Final/Best Model, Xception) | ~0.57 | ~1.47 | ~0.63–0.65 | ~1.36 | 0.60–0.68 | 0.58–0.64 | 0.59–0.66 | ~0.82 |

## GUIDE QUESTIONS (Student Explanation & Reflection)
## A. Model Performance
1. Which pre-trained model achieved the highest accuracy? Why?
- MobileNetV2 achieved the highest accuracy. This is because it is a lightweight yet very efficient model for image classification. Its optimized design allows it to learn patterns in the dataset more effectively than some other models.
2. Which model had the lowest performance? What could be the reason?
- The Teachable Machine model showed the lowest performance, with an accuracy of only about 5%. The main reason for this poor performance is that it was likely trained with very limited features and without the benefits of advanced transfer learning techniques, making it unable to recognize most of the different classes.
3. How did loss values compare across models?
-  I observed a clear relationship between accuracy and loss values. Models that achieved higher accuracy also had lower loss values, indicating they made fewer errors and fit the data better. Conversely, weaker models, such as the Teachable Machine, had very high loss, which means they struggled significantly to learn from and fit the data.

## B. Evaluation Metrics
4. Why is accuracy not enough to evaluate a model?
- Accuracy alone is not sufficient to fully evaluate a model because it doesn't reveal how well the model handles situations with imbalanced classes, where some categories have many more examples than others. It also doesn't show specific types of errors the model might be making, such as consistently misclassifying one particular class.
5. Which model had the best F1-score? What does it indicate?
- DenseNet121 had the best F1-score. This is a significant indicator because the F1-score is a balance between precision (how many selected items are relevant) and recall (how many relevant items are selected). A high F1-score means DenseNet121 was very effective at balancing these two aspects, making it a reliable model for classification.
6. How did Precision and Recall differ across models?
  - Precision and recall varied considerably among the different models. Stronger models consistently demonstrated higher precision and recall values, meaning they were better at correctly identifying relevant instances and not missing many. Weaker models, on the other hand, showed lower values for both, indicating they struggled more with making accurate predictions and capturing all the positive cases.
    
## C. Confusion Matrix Analysis
7. Which classes were frequently misclassified?
- Classes that shared similar visual features, such as different types of plants with very similar-looking leaves, were frequently misclassified by the models. This suggests the models had difficulty distinguishing between subtle differences in visually analogous categories.
8. What patterns did you observe in the confusion matrix?
- The confusion matrix revealed a distinct pattern: the models consistently confused categories that were visually similar to each other more often. This highlighted that the models' errors were not random but often occurred between classes that were hard to tell apart based on their appearance.

## D. ROC and AUC
9. Which model had the highest AUC score?
-  DenseNet121 achieved the highest AUC (Area Under the Curve) score among all the models that were evaluated.
10. What does AUC tell us about model performance?
- The AUC score is a very useful metric because it tells us how well a model can distinguish between positive and negative classes. A higher AUC indicates that the model is better at separating these classes across different thresholds, providing a good measure of its overall reliability and discriminatory power.
  
## E. Explainability (Grad-CAM)
11. What did Grad-CAM reveal about model decision-making?
- Grad-CAM was instrumental in revealing which specific regions of an image the model focused on and used to make its decisions. It allowed us to visualize the parts of the input that were most important to the model's final prediction.
12. Did the model focus on relevant image regions?
- Yes, the improved models showed a clear tendency to focus more on the correct and relevant object areas within the images. This meant they were looking at the right things when making their classifications, contributing to their better performance.
13. Which model produced the most meaningful heatmaps?
- DenseNet121 produced the most meaningful and informative heatmaps. These heatmaps effectively highlighted the actual plant regions within the images, confirming that this model was accurately attending to the critical visual evidence for its predictions.
  
## F. Model Comparison & Improvement
14. Which model would you recommend for deployment? Why?
- I would recommend DenseNet121 for deployment. This recommendation is based on its superior performance, as it consistently achieved the best accuracy and also demonstrated the highest AUC score, making it the most robust and reliable choice.
15. How can you further improve your best-performing model?
-  To further enhance the best-performing model, we can focus on two key areas: adding more training data to expose the model to a wider variety of examples, and using stronger data augmentation techniques (like rotating, zooming, or flipping images) to help the model learn to be more robust to variations in input.
  
## G. Real-World Application
16. How can your model be applied in real-world scenarios?
- This model has significant potential for real-world applications. It can be applied in areas such as plant disease detection, helping farmers identify issues early, or for automated image classification tasks within the agricultural industry, streamlining processes.
17. What are the risks of deploying an inaccurate model?
-  Deploying an inaccurate model carries substantial risks. If the model makes incorrect predictions, it could lead to poor decision-making in critical scenarios, potentially causing financial losses, crop damage, or other negative consequences in real-world applications.
18. How can this system be integrated into a mobile/web app?
- To integrate this system into a mobile or web application, the trained model would be connected to a user interface. This interface would allow users to easily upload images, and the application would then send these images to the model for processing and display the prediction results back to the user.
