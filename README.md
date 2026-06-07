# 🫐 RaspberryPi Box Detection — YOLO26n Model Exports

Trained with **Ultralytics YOLO26n**, this repository provides multiple export formats of an AI model designed to **detect RaspberryPi boxes** in images and video streams. Each format is optimized for a different deployment target, from desktop inference to edge devices.

---

## 📦 Available Formats

### 1. ONNX — `model.onnx`

> **Best for: Desktop & cross-platform inference**

[ONNX (Open Neural Network Exchange)](https://onnx.ai/) is an open standard format for machine learning models. It offers broad compatibility across frameworks and runtimes (e.g. ONNX Runtime, OpenCV DNN, TensorRT).

**Why use it:**
- Flexible and widely supported across platforms and languages
- Strong performance on CPU and GPU (desktop / server)
- Compatible with tools like ONNX Runtime, OpenCV, and more
- Easy integration into Python, C++, C#, Java, and other pipelines

```bash
# Example inference with ONNX Runtime (Python)
pip install onnxruntime
```

---

### 2. PyTorch — `model.pt`

> **Best for: Training, fine-tuning & research**

The native **PyTorch** format is the original checkpoint produced by Ultralytics during training. It is the most feature-complete format and directly usable with the Ultralytics Python library.

**Why use it:**
- Full compatibility with the Ultralytics ecosystem
- Supports further training, fine-tuning, and transfer learning
- Easiest to use for quick prototyping and experimentation
- Required format for re-exporting to other targets

```bash
# Example inference with Ultralytics (Python)
pip install ultralytics
```

```python
from ultralytics import YOLO

model = YOLO("model.pt")
results = model("image.jpg")
results[0].show()
```

---

### 3. TensorFlow Lite — `model.tflite`

> **Best for: Edge deployment on Raspberry Pi & embedded systems**

[TensorFlow Lite](https://www.tensorflow.org/lite) is a lightweight runtime designed for on-device inference. The `.tflite` format is optimized for low-latency, low-power environments — making it the ideal choice for running detection directly on a **Raspberry Pi**.

**Why use it:**
- Minimal memory and CPU footprint
- Runs efficiently on ARM-based processors (e.g. Raspberry Pi 4/5)
- No internet connection required — fully offline inference
- Supports optional INT8 quantization for even faster performance

```bash
# Example inference with TFLite (Python, on Raspberry Pi)
pip install tflite-runtime
```

---

## 📊 Format Comparison

| Format | Extension | Best For | Framework | Edge-Ready |
|---|---|---|---|---|
| ONNX | `.onnx` | Desktop / Cross-platform | ONNX Runtime, OpenCV | ⚠️ Partial |
| PyTorch | `.pt` | Research & Training | Ultralytics / PyTorch | ❌ Heavy |
| TensorFlow Lite | `.tflite` | Edge / Embedded devices | TFLite Runtime | ✅ Yes |

---

## 🤖 Base Model

| Property | Value |
|---|---|
| Architecture | Ultralytics YOLO26n |
| Task | Object Detection |
| Target Class | RaspberryPi Box |
| Framework | [Ultralytics](https://github.com/ultralytics/ultralytics) |

---

## 🚀 Quick Start

**1. Clone the repository**
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

**2. Pick the format that fits your target platform** (see table above)

**3. Install the corresponding runtime and run inference**

---

## 📄 License

This project is released under the [MIT License](LICENSE).  
The YOLO architecture is subject to [Ultralytics licensing terms](https://github.com/ultralytics/ultralytics/blob/main/LICENSE).

---

> Made with ❤️ using [Ultralytics YOLO](https://github.com/ultralytics/ultralytics)
