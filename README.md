# 📚 LeNet-5: A Classic Convolutional Neural Network Architecture
📌 Overview:
- LeNet-5 is one of the earliest and most influential convolutional neural network (CNN) architectures, proposed by Yann LeCun, Léon Bottou, Yoshua Bengio, and Patrick Haffner in 1998.

- It was designed for handwritten digit recognition and tested on the MNIST dataset, achieving high accuracy long before the deep learning revolution.

- This model played a foundational role in the development of modern deep learning for computer vision tasks.

# 📜 Origin and Publication
Paper Title: Gradient-Based Learning Applied to Document Recognition

Authors: Yann LeCun, Léon Bottou, Yoshua Bengio, and Patrick Haffner

Published: 1998 in the Proceedings of the IEEE


# 🧠 Why "LeNet-5"?
The "5" in LeNet-5 refers to the fifth version of the LeNet series. Earlier versions (LeNet-1 to LeNet-4) were also CNNs but with simpler or less effective architectures. LeNet-5 was the most successful and well-documented version, and it became the most cited and widely adopted in educational and experimental settings.

# 🏗️ Architecture Summary
LeNet-5 consists of 7 layers, excluding the input, and includes convolutional, subsampling (pooling), and fully connected layers.

Input:
32×32 grayscale image

MNIST digits are 28×28, so they are zero-padded to 32×32

Layers:

| Layer  | Type                          | Output Size | Description                                                            |
| ------ | ----------------------------- | ----------- | ---------------------------------------------------------------------- |
| Input  | -                             | 32×32×1     | Grayscale image                                                        |
| C1     | Convolution                   | 28×28×6     | 6 filters of size 5×5, stride 1, tanh activation                       |
| S2     | Subsampling (Average Pooling) | 14×14×6     | 2×2 average pooling, stride 2                                          |
| C3     | Convolution                   | 10×10×16    | 16 filters (some connected to specific maps in S2), size 5×5           |
| S4     | Subsampling                   | 5×5×16      | 2×2 average pooling, stride 2                                          |
| C5     | Convolution                   | 1×1×120     | 120 filters of size 5×5 (connected to entire 5×5 feature maps from S4) |
| F6     | Fully Connected               | 84 units    | Fully connected layer, tanh activation                                 |
| Output | Fully Connected               | 10 units    | One for each digit class (0–9), softmax applied during inference       |


# ⚙️ Technical Details
1. Activation Functions
LeNet-5 used tanh or sigmoid instead of ReLU, which was not common at the time.

2. Pooling
Average pooling was used instead of modern max pooling.

3. Parameter Sharing
Introduced weight sharing in convolution layers to reduce the number of parameters.

4. Sparse Connectivity
Not all feature maps in C3 are connected to all feature maps in S2 to encourage feature diversity.

# 🆚 LeNet-5 vs Modern CNNs

| Feature        | LeNet-5         | Modern CNNs (e.g., ResNet, VGG)       |
| -------------- | --------------- | ------------------------------------- |
| Depth          | 7 layers        | 50–100+ layers                        |
| Activation     | tanh/sigmoid    | ReLU / GELU                           |
| Pooling        | Average pooling | Max pooling                           |
| Optimization   | SGD             | SGD, Adam, RMSprop                    |
| Regularization | None            | Dropout, BatchNorm                    |
| Training Data  | MNIST (small)   | Large-scale datasets (ImageNet, etc.) |
| Hardware       | CPU             | GPU/TPU optimized                     |


# 🧪 Use Cases
- Digit recognition (e.g., MNIST)

- Early experiments in document recognition and computer vision

- Educational tutorials in deep learning

