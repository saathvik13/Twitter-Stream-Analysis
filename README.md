# Twitter-Stream-Analysis

### 1. twitter.mat holds two Term-Frequency (TF) matrices Xtr and Xte. It also contains YtrMat and YteMat, the target variables in the one-hot vector format.
### 2. Each column of the TF matrix Xtr can be either “positive”, “negative”, or “neutral”, which are represented numerically as 1, 2, and 3 in the YtrMat. They are sentimental classes of the original twits.
### 3. Learn 50 PLSI topics B ∈ R891×50 and their weights Θtr ∈ R50×773 from the training data Xtr, using the ordinary PLSI update rules.
### 4. Reduce the dimension of Xte down to 50, by learning the weight matrix Θte ∈ R50×193. This can be done by doing another PLSI on the test data Xte, but this time by reusing the topic matrix B you learned from the training set. So, you skip the update rule for B. You only update Θte ∈ R50×193.
### 5. Define a perceptron layer for the softmax classification. This part is similar to the case with kernel PCA with a perceptron. Instead of the kernel PCA results as the input to the perceptron, you use Θtr for training, and Θte for testing. This time the number of output units is 3 as there are three classes, and that’s why the target variable YtrMat is with three elements. Review M6 S37-39 to review what softmax is.
### 6. Report your classification accuracy.
### 7. Note: do NOT use any deep learning framework that supports softmax implementation and automatic gradient computation. Use your own implementation of softmax and backpropa- gation.
