git clone https://github.com/ardamavi/Sign-Language-Digits-Dataset

How images are stored:
Sign-Language-Digits-Dataset/Dataset/N[0-9]/IMG_N.JPG

Source video: https://www.youtube.com/watch?v=qFJeN9V1ZsI&t=1256s

It was able to achieve 92% val accuracy. And I was able to achieve 94% val accuracy using custom optimization approaches and the same base model.

MLE in source video removed head layers from the model and unfreezed 20/30 layers, trained it and got 92% val accuracy.

In the Jupyter Notebook can be seen the experimentation done to get 94% val accuracy. 

1. First we check which mobilenet version works better (just for curiousity). Keep using V1 since has the best performance and is the same used in the source project (so that we can better compare optimization methods).
2. Mobilenetv1 freezed w/ trainable dense layer of 10 returned 86% val accuracy.
3. Tried to use mobilenetv1 freezed as a feature extractor and pass it to Xgboost for classification, but only got 81% val accuracy.
4. Then tried to add a more sofisticated head rather than just a dense layer of 10. Which got me a val accuracy of 88%.
5. Re-trained that model w/ last 35 layers unfrozen and got 92% val accuracy.
6. Re-trained the model of step 2 w/ last 30 layers unfrozen and got 94% val accuracy.
7. With that last model, tested on never seen images and got a 97% test accuracy.

