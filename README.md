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
- Validation accuracy: 81%, driven primarily by correct classification of benign lesions.
- Confusion matrix analysis revealed strong class imbalance effects.
- Benign recall was very high (0.99), indicating reliable identification of non-cancerous cases.
- Malignant recall was low (0.07), with 368 out of 395 malignant cases misclassified as benign.
- This demonstrates that accuracy alone is insufficient for evaluating medical image classifiers and highlights the need for imbalance-aware training strategies.


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
