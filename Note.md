-Tensorflow: tensor + flow   
-Tensor is just a fancy word for a multi-dimensional array  
-Tensorflow is an end-to-end deep learning framework.  
A framework is like a toolbox that gives you everything you need to build and train machine learning models. So you can just focus on building the model, not creating everything from scratch.  
Other popular framework: Pytorch, Keras.

Main goal should be to improve val_accuracy (validation accuracy)

### Typical Good Accuracy Ranges

| Training Accuracy | Validation Accuracy | Interpretation                                  |
|-------------------|---------------------|--------------------------------------------------|
| 0.90              | 0.88                | Very good, slight generalization gap.         |
| 0.95              | 0.90                |  Great model, well-trained.                    |
| 1.00              | 0.70                |  Overfitting — model memorized training data.  |
| 0.85              | 0.85                |  Solid start — try improving both.             |
| 0.80              | 0.60                |  Underfitting or data issues.                  |
| 0.70              | 0.70                |  Possibly okay on very hard or noisy data.     |

Stable validation loss means that the model is performing consistently on data it hasn’t seen before (the validation set) during training.

| Epoch | Training Accuracy | Validation Accuracy | Training Loss | Validation Loss |
|-------|-------------------|----------------------|----------------|------------------|
| 1     | 0.65              | 0.63                 | 0.65           | 0.64             |
| 2     | 0.74              | 0.70                 | 0.54           | 0.58             |
| 3     | 0.80              | 0.74                 | 0.42           | 0.55             |
| 4     | 0.85              | 0.75                 | 0.34           | 0.53             |
| 5     | 0.88              | 0.75                 | 0.29           | 0.52             |
| 6     | 0.91              | 0.75                 | 0.24           | 0.51             |
| 7     | 0.92              | 0.76                 | 0.20           | 0.51             |

Validation loss can fluctuate a little from epoch to epoch due to random variation. One small increase doesn’t always mean the model is overfitting. It might decrease again in the next epoch.
Use a technique called early stopping, which stops training when the validation loss hasn’t improved for a few consecutive epochs.
```
from tensorflow.keras.callbacks import EarlyStopping

early_stop = EarlyStopping(monitor='val_loss', patience=3, restore_best_weights=True)

model.fit(train_generator,
          validation_data=test_generator,
          epochs=30,
          callbacks=[early_stop])
```
