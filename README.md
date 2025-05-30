# Federated-Image-Reconstruction

🧠 Denoising Autoencoder with Differential Privacy and Gaussian Noise
This project implements a convolutional denoising autoencoder trained on the CIFAR-10 dataset to reconstruct noisy images. It supports Gaussian noise, Differential Privacy (DP) noise, and demonstrates visual and quantitative comparisons using PSNR (Peak Signal-to-Noise Ratio).

📌 Objectives

✅ Reconstruct clean images from noisy inputs using an autoencoder

✅ Compare traditional denoising (Gaussian Blur) with learned reconstruction

✅ Explore the impact of Differential Privacy noise

✅ Visualize and quantify reconstruction quality using PSNR

🛠️ Technologies Used

TensorFlow/Keras – Model architecture & training

NumPy / OpenCV – Image manipulation

Matplotlib – Visualization

Scikit-Image – PSNR evaluation

Google Colab – Interactive execution environment

🧰 Key Features

🔧 Autoencoder Architecture
Encoder:

Two convolutional layers with batch normalization and max-pooling

Decoder:

Transposed convolutions and skip connections for reconstruction

Skip Connections: Help recover fine-grained image details

Loss Function: MSE (Mean Squared Error)

📶 Noise Injection

Gaussian Noise:

Added using np.random.normal()

Standard deviation = 30

Differential Privacy (DP) Noise:

Computed with Gaussian mechanism:

𝜎
=
sensitivity
⋅
2
log
⁡
(
1.25
/
𝛿
)
𝜖
σ= 
ϵ
sensitivity⋅ 
2log(1.25/δ)
​
 
​
 
Lower epsilon ⇒ higher privacy ⇒ more noise

🧪 Evaluation Metric

PSNR (Peak Signal-to-Noise Ratio):

Used to quantify reconstruction quality

Higher PSNR = better reconstruction

📁 How It Works

Train or Load Model:

Automatically loads best_denoiser.h5 if exists

Otherwise, trains a new autoencoder using CIFAR-10

Upload Image:

Users upload a custom image (auto-resized to 32×32)

Noise Injection:

Gaussian noise and DP noise are added to the image

Denoising Options:

Gaussian Blur (baseline)

Autoencoder Reconstruction on:

Gaussian noisy image

DP noisy image

Visualization:

Displays 5 images:

Noisy input

Denoised via Gaussian blur

DP noisy input

Reconstructed (Gaussian)

Reconstructed (DP)

PSNR values are shown for each

📊 Sample Output
The output includes reconstructed images like:

Title	Description
Noisy Input	Original + Gaussian Noise
Denoised (Gaussian)	Filtered using OpenCV
DP Version Input	Original + DP Gaussian Noise
Reconstructed (Noisy)	Autoencoder result (Gaussian)
Reconstructed (DP)	Autoencoder result (DP noise)

Each image is annotated with PSNR in dB for comparison.

🚀 Try It on Google Colab

You can run the full notebook interactively using Google Colab.


📚 References

Autoencoders in Deep Learning

Differential Privacy — Google AI

PSNR Metric

