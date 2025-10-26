
# 🧠 Neural Network Project — ML S5 CSE

> A custom-built **Feedforward Neural Network in C++** designed to learn the linear function
> [
> y = 10x + 18
> ]
> using sigmoid and leaky ReLU activations.
> This project demonstrates the fundamentals of backpropagation, layer design, and gradient-based learning.

---

## ⚙️ Configuration & Setup

### 🧩 **Network Initialization**

```cpp
node_list = {
    {{ACT_FUN::sigmoid, 2.0}, {ACT_FUN::sigmoid, 3.0}, {ACT_FUN::sigmoid, 5.0}},
    {{ACT_FUN::leaky_relu, 4.0}, {ACT_FUN::leaky_relu, 4.0}, {ACT_FUN::leaky_relu, 4.0}},
    {{ACT_FUN::leaky_relu, 7.0}, {ACT_FUN::leaky_relu, 3.0}, {ACT_FUN::leaky_relu, 3.0}}
};

_nn.initialize(node_list);
```

---

## 🧠 Network Architecture

| **Layer** | **Type**     | **Neurons** | **Activation Function** |
| --------- | ------------ | ----------- | ----------------------- |
| Layer 0   | Input Layer  | 3           | `sigmoid`               |
| Layer 1   | Hidden Layer | 3           | `leaky_relu`            |
| Layer 2   | Output Layer | 3           | `leaky_relu`            |

---

## 📊 Dataset Details

The dataset follows the mapping **y = 10x + 18**, with 3 sets of inputs and expected outputs:

| **Input (x₁, x₂, x₃)** | **Expected Output (y₁, y₂, y₃)** |
| ---------------------- | -------------------------------- |
| (1, 2, 3)              | (28, 38, 48)                     |
| (0, 4, 5)              | (18, 58, 68)                     |
| (6, 7, 8)              | (78, 88, 98)                     |

```cpp
std::list<Dataset> datasets = {
    {{1, 2, 3}, {28, 38, 48}},
    {{0, 4, 5}, {18, 58, 68}},
    {{6, 7, 8}, {78, 88, 98}},
};
```

---

## 🔧 Training Configuration

| **Parameter**       | **Value**                |
| ------------------- | ------------------------ |
| **Initial Weights** | 1.0                      |
| **Learning Rate**   | 0.001                    |
| **Error Threshold** | 0.001                    |
| **Epochs**          | 10                       |
| **Loss Function**   | Mean Squared Error (MSE) |

---

## 🚀 Execution Flow

1. **Initialize** the network with the given structure (`sigmoid → leaky_relu → leaky_relu`).
2. **Feedforward**: Pass input values through each layer.
3. **Compute Error**: Compare predicted and target values using MSE.
4. **Backpropagate**: Adjust weights using gradients.
5. **Repeat** for all epochs or until the error threshold is reached.

---

## 🧾 Sample Output

```
Input: [1.000000 2.000000 3.000000]
Label: [28.000000 38.000000 48.000000]
Output: [29.403426 39.956589 50.219187]
Error: [-1.473769 -2.057333 -2.321787]

Input: [0.000000 4.000000 5.000000]
Label: [18.000000 58.000000 68.000000]
Output: [18.610650 55.691571 65.831840]
Error: [-0.631367 2.216553 2.099029]

Input: [6.000000 7.000000 8.000000]
Label: [78.000000 88.000000 98.000000]
Output: [60.719402 83.468694 93.680455]
Error: [13.452148 4.297980 4.129153]
```

---

## 💡 Observations

* 🧮 **Initial predictions** show moderate deviations, reducing with each iteration.
* ⚡ **Sigmoid** smooths input values and stabilizes gradients.
* 🔁 **Leaky ReLU** avoids dead neurons and supports continuous gradient flow.
* 🎯 **Small learning rate (0.001)** ensures steady, stable convergence.

---

## 🧰 Tools & Technologies

* **Language:** C++
* **Libraries:** STL (`list`, `cmath`)
* **Concepts Implemented:**

  * Feedforward Propagation
  * Backpropagation Algorithm
  * Custom Activation Functions
  * Mean Squared Error Calculation

---

## 👩‍💻 Author

**Dharshana K S**
📍 Dept. of Computer Science & Engineering
🎓 TCR23CS030 – ML S5 CSE