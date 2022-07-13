# Digit-Recognizer

Using the **Keras** and **Tensorflow** libraries, I have created a neural network that can accurately classify images of digits. Using the **MNIST Digits dataset**, I created my training and test set (can be located under `Data/Kaggle MNIST Digits/`). 

Documentation of the entire project is viewable through the uploaded **`DigitRecognizer.ipynb`** file.

After conducting EDA on the dataset, I created an Aritifical Neural Network with a simple feedforward mechanism. The Sequential model consisted of the following:

- **Input Layer**: Containing 28\*28 number of neurons (as images were represented by the pixel intensity values within each of the squares on a 28*28 grid).
- **Hidden Layer**: 1 hidden layer containing 256 neurons utilizing the _ReLU_ activation function.
- **Output Layer**: Containing 10 neurons (corresponding to each digit class) utilizing the _Softmax_ Activation function.
- **Loss Function**: _CategoricalCrossentropy_ to evaluate performance across training cycles. This is because our data involves One Hot Encoding.
- **Optimizer**: The _Adam Algorithm_ to control the backpropagation process.
- **Regularization**: _Early Stopping_, which monitors changes in the Validation set's accuracy, and terminates training in case there is no improvement in it for a preset number of training cycles.

This helped me achieve a **93.99% accuracy** on my validation set.
***
I then improved my model through the following modifications:

- **Hidden Layer**: 3 hidden layers containing 256, 128, 64 neurons respectively.

This helped me achieve a **97.07% accuracy** on my validation set.
***
I then proceeded to create a Convolutional Neural Network to further improve my model. The CNN helps in reducing the size of the input, allowing small shifts in image structures, and identifying correlations between neighbouring pixels in an image. 

I made the following modifications:

- **Padding**: _Zero Padding_, so as to weigh edge values of the image equally during convolvement.
- **Filtering**: Our first set contained 32 filters each of size 5\*5, and our second set contained 64 filters of size 3\*3 each with a 2\*2 stride.
- **Pooling**: Our first pooling layer is of the size 2\*2 and the second is of the size 2\*2 with a 2\*2 stride in order to _downscale_.
- **Optimization**: _ReduceLROnPlateau_, which scales down the learning rate when the accuracy of the Validation set shows no improvement for a preset number of training cycles.

This helped me achieve a **99.1% accuracy** on my validation set. Below I have attached the final **Confusion Matrix** used to evaluate my model's performance.

![image](https://user-images.githubusercontent.com/69107788/178077877-785df022-613c-4cae-8f01-6ca9439b5e84.png)
