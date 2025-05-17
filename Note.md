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
