# AI / Machine Learning Notes

## 📌 Key Concepts

### What is Machine Learning?
ML is a subset of AI that enables systems to learn and improve from experience.

## 🤖 ML Types

| Type | Description | Example |
|------|-------------|---------|
| **Supervised** | Labeled data | Image classification |
| **Unsupervised** | Unlabeled data | Customer clustering |
| **Reinforcement** | Reward-based | Game playing |

## 🧠 Deep Learning

### Neural Network Basics

```python
import tensorflow as tf

model = tf.keras.Sequential([
    tf.keras.layers.Dense(128, activation='relu', input_shape=(784,)),
    tf.keras.layers.Dropout(0.2),
    tf.keras.layers.Dense(64, activation='relu'),
    tf.keras.layers.Dense(10, activation='softmax')
])

model.compile(
    optimizer='adam',
    loss='categorical_crossentropy',
    metrics=['accuracy']
)
```

### CNN Architecture

```
Input (224x224x3)
    ↓
Conv2D + ReLU (32 filters)
    ↓
MaxPooling (2x2)
    ↓
Conv2D + ReLU (64 filters)
    ↓
MaxPooling (2x2)
    ↓
Conv2D + ReLU (128 filters)
    ↓
MaxPooling (2x2)
    ↓
Flatten
    ↓
Dense (512) + Dropout
    ↓
Softmax (10 classes)
```

## 🔧 Key Libraries

| Library | Purpose |
|---------|---------|
| TensorFlow | Deep learning framework |
| PyTorch | Alternative DL framework |
| Scikit-learn | Classical ML algorithms |
| Hugging Face | NLP transformers |
| OpenCV | Computer vision |
| Pandas | Data manipulation |

## 📊 Data Preprocessing

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler

# Load data
df = pd.read_csv('data.csv')

# Split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# Scale
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)
```

## 📚 Resources

- [TensorFlow Tutorials](https://www.tensorflow.org/tutorials)
- [Hugging Face Course](https://huggingface.co/learn/nlp-course)
- [Fast.ai](https://www.fast.ai/)

---
*Notes by Rushikesh*
