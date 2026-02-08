# Skin Cancer Detection using Machine Learning

## Objective
To build a convolutional neural network (CNN) that classifies dermoscopic skin lesion images as benign or malignant, with emphasis on minimizing missed cancer cases.

## Dataset
- Source: Kaggle – Skin Cancer Dataset (tsaideepak/skin-cancer)
- Data consists of dermoscopic images organized into class-wise train and validation folders.
- Labels are inferred from directory structure.

## Approach
- Reformulated the original multi-class problem into binary classification:
  - Malignant: mel, bcc, akiec
  - Benign: nv, bkl, df, vasc
- Images resized to 128×128 and normalized.
- Trained a baseline CNN from scratch.
- Addressed class imbalance using class weighting.
- Evaluated using confusion matrix, precision, recall, and F1-score.

]## Results

Two models were evaluated: a baseline CNN and Logistic Regression, using a held-out validation set of 2,015 images.

### CNN (Baseline)
- Validation Accuracy: ~81%
- Benign Recall: ~0.99
- Malignant Recall: ~0.07
- Confusion matrix analysis showed that 368 out of 395 malignant cases were misclassified as benign.
- The model exhibited strong bias toward the majority (benign) class, making accuracy misleading for medical evaluation.

### Logistic Regression (Classical Baseline)
- Validation Accuracy: ~80%
- Malignant Recall: ~0.32 (126 / 395 malignant cases correctly identified)
- Precision (Malignant): ~0.47
- False negatives reduced significantly compared to the CNN baseline, at the cost of increased false positives.

### Key Takeaway
Although both models achieved similar accuracy, Logistic Regression detected substantially more malignant cases. This comparison demonstrates that accuracy alone is insufficient for medical image classification and highlights the importance of recall-focused evaluation under class imbalance.


## Limitations
- Dataset is highly imbalanced.
- Image resolution limited to 128×128.
- Model trained from scratch without pretrained features.
- Not suitable for clinical deployment without further validation.

## Future Work
- Use transfer learning (ResNet / EfficientNet).
- Increase image resolution after pipeline validation.
- Tune decision threshold to further improve malignant recall.
- Evaluate on an external dataset.
