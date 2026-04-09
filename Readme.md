# Sign Language Digits Classifier

A transfer learning project that classifies hand signs for digits 0–9 using MobileNetV1 and Keras.

## Stack

- Keras (TensorFlow backend)
- MobileNetV1 (pretrained on ImageNet)
- XGBoost (tested as alternative classifier)

## Dataset

```
git clone https://github.com/ardamavi/Sign-Language-Digits-Dataset
```

Images are stored as: `Sign-Language-Digits-Dataset/Dataset/N[0-9]/IMG_N.JPG`

## Results

- Baseline (source video MLE): **92% val accuracy** — unfroze last 20/30 layers of MobileNetV1
- This project: **94% val accuracy** — achieved via custom optimization
- Test accuracy on unseen images: **97%**

## Approach (see notebook for details)

1. Compared MobileNet versions — V1 performed best, kept for fair comparison with source
2. MobileNetV1 frozen + dense(10) head → 86% val accuracy
3. MobileNetV1 as feature extractor → XGBoost → 81% val accuracy
4. Richer head architecture → 88% val accuracy
5. Step 4 model + last 35 layers unfrozen → 92% val accuracy
6. Step 2 model + last 30 layers unfrozen → **94% val accuracy** (best)
7. Best model tested on never-seen images → **97% test accuracy**

## Reference

Source video: https://www.youtube.com/watch?v=qFJeN9V1ZsI&t=1256s
