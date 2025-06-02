# 🧬 Conditional GAN – Blood Cell Image Generator  
**Python · PyTorch · torchvision · Jupyter Notebooks**

A deep learning model that generates blood cell images, conditioned on specific cell types using a Conditional GAN architecture.

---

## ✨ Features

🔬 **Conditional Image Generation**  
&emsp;Generate 64x64 pixel RGB images based on selected blood cell type:
- Benign  
- Pre-B  
- Pro-B  
- Early Pre-B

🧠 **Deep Generative Modeling**  
&emsp;Implemented using:
- Conditional GAN (Generator + Discriminator)
- Label embedding + one-hot class conditioning
- Tanh normalization and LeakyReLU activations

📊 **Loss Tracking + Visualization**  
&emsp;Real-time plot of Generator and Discriminator losses during training.

🖼️ **Live Sample Viewer**  
&emsp;Generates preview images every 20 epochs using:
- Grid layout with `torchvision.utils.make_grid`
- Optional GUI selection via `ipywidgets` + `matplotlib`

💾 **Model Checkpointing**  
&emsp;Saves model weights every 20 epochs or when Generator improves.

⚠️ **Early Stopping**  
&emsp;Stops training when Generator loss doesn't improve for 30 epochs.

---

## 🗂 Dataset

https://www.kaggle.com/datasets/mohammadamireshraghi/blood-cell-cancer-all-4class

The dataset should be organized as follows:

```
BloodCells_Cancer/
├── Benign/
├── Pre-B/
├── Pro-B/
└── Early Pre-B/
```

Each folder should contain `.jpg` or `.png` images of the corresponding cell type.

---

## ⚙️ Tech Stack

- 🔥 **PyTorch** – Deep learning framework  
- 🖼 **torchvision** – Image transformation & visualization  
- 📊 **matplotlib** – Plotting training loss & generated samples  
- 💡 **ipywidgets** – Interactive dropdown & image generator  
- 📁 **PIL** / **glob** – Image loading and preprocessing

---

## 🚀 How to Run

1. **Install dependencies**
```bash
pip install torch torchvision matplotlib ipywidgets pillow
```

2. **Clone and navigate to the project**
```bash
git clone https://github.com/yourusername/blood-cell-cgan.git
cd blood-cell-cgan
```

3. **Prepare dataset**  
Place the `BloodCells_Cancer/` directory in the project root with the structure above.

4. **Train the model**  
Run the notebook or training script:
```bash
python train.py
```

5. **Launch the image generator GUI** (optional, Jupyter):
```python
display(ui)
```

---

## 📈 Sample Loss Plot

```python
plt.plot(g_losses, label='Generator')
plt.plot(d_losses, label='Discriminator')
plt.title("Training Loss")
plt.xlabel("Epoch")
plt.ylabel("Loss")
plt.legend()
plt.show()
```

---

## 📸 Example Output

<p align="center">
  <img src="samples/generated_epoch_100.png" width="300"/>
</p>

---

## 📜 License

MIT License © 2025 [Your Name]
