# USC-EE-541-HW5
USC MLDS
# Analysis

### i. How to determine a learning rate?
I tested learning rates of 0.001, 0.005, 0.01, 0.05, and 0.1 using my `find_optimal_learning_rate` function. For each rate, I trained a model and selected the one with lowest validation loss. My approach included visualization of training and validation losses to compare convergence behavior.

### ii. Method used to establish model convergence
Implemented convergence detection with:
- Tolerance threshold of 1e-6
- Tracking changes in training loss between iterations
- Requiring 5 consecutive iterations with minimal change to confirm convergence
- Resetting the counter for significant loss changes

This prevented false convergence signals from random fluctuations and provided efficient early stopping.

### iii. Regularizers tried and their impact
I tested these:
- No regularization
- L1 regularization (λ=0.001, 0.01)
- L2 regularization (λ=0.001, 0.01, 0.1)

L1 regularization created sparse weights and performed feature selection. L2 regularization prevented overfitting by keeping weights small. Unregularized models fit training data well but showed worse generalization. I selected the regularization approach with best validation performance.

### iv. Learning curve plots
1. Log-loss for training and test sets vs. iteration number (log scale)
2. Accuracy for training and test sets vs. iteration number

These visualizations helped diagnose overfitting/underfitting and assess model generalization.

### v. Binary classification results
Implemented binary classification with a 0.5 threshold for digit "2" detection. The evaluation metrics include:
- Final loss (with regularization)
- Accuracy, precision, recall, and F1 score

I saved the trained weights (784-dim vector) and bias (scalar) to 'digit_classifier_weights.h5' using the keys 'w' and 'b' as required.

PS:  I used the data from HW3, but it was a bit strange, and I couldn’t get good predictions. So, I downloaded the MNIST data online. The images and labels are the same.
