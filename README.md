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

## Results
- Baseline CNN achieved ~80% validation accuracy.
- Accuracy alone was insufficient due to class imbalance.
- Introducing class weights improved recall for malignant cases, at the cost of higher false positives.
- Model behavior aligns with medical priorities where missing cancer is more costly than false alarms.

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
