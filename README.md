# CNN Pipeline Simulator

An interactive, educational single-page web application designed to demystify the inner workings of a Convolutional Neural Network (CNN). Built specifically for geometric shape classification (Square, Triangle, Circle), this tool bridges the gap between abstract mathematical concepts and practical deep learning code.

---

## 🚀 Key Features & Pipeline Steps

The application breaks down the complete deep learning lifecycle into 9 structured, interactive steps:

1. **Data Split & Cross-Validation**: Explains the rationale behind dividing datasets into Training (80%), Validation (10%), and Test (10%) sets, alongside 5-Fold Cross-Validation logic.
2. **Input Image (RGB)**: Visualizes a synthetic 3D tensor matrix ($224 \times 224 \times 3$) representing red, green, and blue color channels.
3. **Normalization**: Demonstrates Z-Score normalization per channel to standardize pixel values around a mean of 0.
4. **Layer 1 (Basic Feature Extraction)**: Explores 16 convolutional filters ($3 \times 3$), ReLU activation, and 2x2 Average Pooling to detect basic lines and edges.
5. **Layer 2 (Intermediate Patterns)**: Explores 32 filters that combine edges into corner structures and mid-level geometric cues.
6. **Layer 3 (Object Understanding)**: Explores 64 filters leveraging expanded *receptive fields* to comprehend whole shapes (e.g., complete circles).
7. **Output & Classification (Softmax)**: Demonstrates the Flatten operation ($50,176$ parameters), Fully Connected layers, and One-Hot Encoding comparison to compute categorical cross-entropy loss.
8. **Training & Optimization**: An interactive live-training curve simulator illustrating Epochs, Learning Rate impacts, Dropout (Regularization), and **Early Stopping** to prevent overfitting.
9. **Inference & Model Deployment**: Explores the exact dictionary structure stored inside a trained model file (`.h5` / `.pth`) and explains stateless real-world inference.

---

## 🧠 Core Deep Learning Concepts Explained

### 1. The Training Loop & Loss Function
Computers evaluate their performance by comparing model predictions against ground-truth labels using **Categorical Cross-Entropy Loss**. The resulting error score drives the learning loop.

### 2. Backpropagation & Gradient Descent
* **Backpropagation:** Propagates the error signal backward through the network using partial derivatives (calculus) to find which filters contributed most to the mistake.
* **Gradient Descent:** The iterative process of stepping in the direction opposite to the gradient to minimize the loss function.
* **Adam Optimizer:** An advanced optimizer utilizing adaptive momentum estimation to dynamically adjust learning steps.

### 3. Regularization (Dropout)
Randomly deactivates a percentage of neurons during training to prevent the network from blindly memorizing training samples (*overfitting*), forcing it to learn robust structural features instead.

---

## 📂 Anatomy of Saved Model Files (`model_terbaik.h5` / `.pth`)

A saved model file contains **no images or text**, but rather a dictionary of raw tensor weights and biases:

* **`conv1.weight` to `conv3.weight`**: Matriks kernel $3 \times 3$ representing the learned feature detectors.
* **`bias`**: Constant values added prior to activation functions to shift thresholds.
* **`fc.weight` & `fc.bias`**: The large weight matrix mapping thousands of flattened features to final classification probabilities.

---

## 🛠️ Tech Stack & Requirements

* **HTML5 & CSS3** with **Tailwind CSS** (via CDN).
* **Vanilla JavaScript** (ES6+) for interactive canvas rendering, live loss simulation charts, and dynamic modal controls.
* **PyTorch** code reference snippets provided for every individual stage.

---

## 💻 Running the Simulator

Simply open the `cnn_simulator.html` file in any modern web browser. No installation, server, or external dependencies are required.
Simulasi Neural Network bisa kamu coba di https://playground.tensorflow.org/
