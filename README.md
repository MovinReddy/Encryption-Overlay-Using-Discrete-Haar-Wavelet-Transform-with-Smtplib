# Encryption-Overlay-Using-Discrete-Haar-Wavelet-Transform-with-SmtChaos-Based Image Encryption with Haar Wavelet Transform and Email Transmission
📌 Overview
This project implements a chaos-based encryption technique combined with the Discrete Haar Wavelet Transform (DHWT) to securely encrypt an image and overlay it with another image. The final result is sent as an email attachment. The technique utilizes the logistic map for chaotic key generation, making the encryption highly secure and non-linear.

🧠 Features
2D Discrete Haar Wavelet Transform (DHWT) for image decomposition.

Chaos-based image encryption using the logistic map.

Image overlay with an additional layer.

Encrypted image email transmission using SMTP with optional app-password authentication.

📦 Dependencies
numpy

pywt (PyWavelets)

Pillow (PIL)

matplotlib

smtplib, email (Python standard library)

io, base64 (Python standard library)

pip install numpy pywt Pillow matplotlib
⚙️ How It Works
Image Loading: The input image is read using Pillow and converted into a NumPy array.

Encryption:

The image is split into R, G, and B channels.

Each channel is flattened and concatenated.

A chaotic sequence is generated using the logistic map.

Pixels are permuted based on the chaotic sequence.

Overlay Image:

An additional image is resized and transposed.

The overlay is generated using the pixel-wise maximum between the two images.

Export and Send:

The final image is saved in memory using BytesIO.

The image is attached to an email and sent using smtplib.

🔐 Encryption & Decryption Logic
Chaotic Key Generation: Utilizes the logistic map to generate pseudo-random sequences.

Permutation: Applies the permutation indices to shuffle pixel values.

Reversibility: The decrypt_image() function restores the image using the reverse permutation.

📧 Email Configuration
Before running, configure:

python
Copy
Edit
sender_email = "your_email@example.com"
receiver_email = "receiver_email@example.com"
app_password = "your_app_password"
⚠️ Note: Use an app password if using Gmail.

🖼️ Input/Output Example
Input: Original image (.jpg, .png)

Output: encrypted_image_with_additional_layer.jpg sent to specified email
