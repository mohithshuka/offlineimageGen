<div align="center">

#  OfflineImageGen

### AI Image Generation — Fully On-Device

**Generate stunning images from text prompts using Stable Diffusion, 100% offline.**  
No internet. No subscriptions. No API keys. Your prompts never leave your phone.

<br/>

[![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)](https://kotlinlang.org)
[![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://developer.android.com)
[![ONNX Runtime](https://img.shields.io/badge/ONNX_Runtime-005CED?style=for-the-badge&logo=onnx&logoColor=white)](https://onnxruntime.ai)
[![Stable Diffusion](https://img.shields.io/badge/Stable_Diffusion-FF6F00?style=for-the-badge&logo=adobeillustrator&logoColor=white)](https://stability.ai)
[![License](https://img.shields.io/badge/License-Educational-lightgrey?style=for-the-badge)](LICENSE)

</div>

---

## ✨ Features

| Feature | Description |
|---|---|
| 🎨 **Text-to-Image** | Generate images from any text prompt |
| 🔒 **100% Offline** | No internet needed after initial setup |
| ⚡ **On-Device Inference** | Runs directly on your Android hardware |
| 💾 **Local Storage** | Save generated images to your device |
| 🚫 **No API Keys** | Completely free to use, forever |
| 🔐 **Privacy-First** | Prompts and images never leave your device |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Kotlin |
| Platform | Android SDK |
| Inference Engine | ONNX Runtime |
| Model Architecture | Stable Diffusion |
| Tokenizer | CLIP Tokenizer |
| Scheduler | DDIM Scheduler |

---

## 🏗️ Project Structure

```
app/
├── src/main/
│   ├── java/com/offlineimagegen/
│   │   ├── MainActivity.kt                 # Entry point & UI
│   │   ├── ImageGenerationEngine.kt        # Core SD pipeline
│   │   ├── ImageGenerationViewModel.kt     # State management
│   │   ├── DDIMScheduler.kt               # Denoising scheduler
│   │   ├── SimpleClipTokenizer.kt          # Text tokenization
│   │   └── ImageSaver.kt                   # Local storage handler
│   │
│   └── assets/
│       ├── text_encoder.onnx               # CLIP text encoder
│       ├── unet.onnx                       # Denoising UNet
│       ├── vae_decoder.onnx                # Latent → image decoder
│       ├── merges.txt                      # BPE merge rules
│       └── vocab.json                      # Tokenizer vocabulary
```

---

## 🚀 How It Works

```
  Text Prompt
      │
      ▼
  ┌─────────────────────┐
  │   CLIP Tokenizer    │  ← Converts text → tokens
  └────────┬────────────┘
           │
           ▼
  ┌─────────────────────┐
  │   Text Encoder      │  ← Tokens → semantic embeddings
  └────────┬────────────┘
           │
           ▼
  ┌─────────────────────┐
  │  DDIM Scheduler +   │  ← Iteratively denoises
  │  UNet               │    latent representations
  └────────┬────────────┘
           │
           ▼
  ┌─────────────────────┐
  │   VAE Decoder       │  ← Latents → pixel image
  └────────┬────────────┘
           │
           ▼
     Generated Image 🖼️
```

1. User enters a text prompt
2. The **CLIP tokenizer** converts the prompt into token IDs
3. The **text encoder** transforms tokens into rich semantic embeddings
4. The **DDIM scheduler** orchestrates iterative denoising steps
5. The **UNet** predicts noise residuals at each step
6. The **VAE decoder** converts the final latent tensor into a full image
7. The image is displayed and can be saved to local storage

---

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/mohithshuka/offlineimageGen.git
cd offlineimageGen
```

### 2. Open in Android Studio

1. Launch **Android Studio**
2. Select **Open Existing Project**
3. Navigate to the cloned folder
4. Wait for **Gradle sync** to complete

### 3. Add Model Files

> ⚠️ Model files are not included in the repository due to size constraints.

Download the required ONNX model files and place them in `app/src/main/assets/`:

```
app/src/main/assets/
├── text_encoder.onnx
├── unet.onnx
├── vae_decoder.onnx
├── merges.txt
└── vocab.json
```

### 4. Run the App

Connect an Android device or start an emulator, then click **Run ▶️**.

---

## 📷 Screenshots

> Add screenshots here to showcase your app!

 Result
<img width="1886" height="1006" alt="Screenshot 2025-10-21 233715" src="https://github.com/user-attachments/assets/fad8d15d-8ffb-4666-bb89-00c45de09059" />

---

## Download the app

> set this project in your android studio
> https://github.com/mohithshuka/offlineimageGen/edit/main/README.md

---

## 🔒 Privacy

Unlike cloud-based AI image generators, OfflineImageGen performs all inference **entirely on-device**.

- ✅ Prompts are **never uploaded**
- ✅ Images are **never transmitted**
- ✅ No user data is **collected or stored remotely**
- ✅ Works in **airplane mode**

Your creativity stays private. Always.

---

## 🎯 Roadmap

- [ ] Negative prompts support
- [ ] Adjustable inference steps
- [ ] Image-to-image generation
- [ ] Inpainting support
- [ ] Model switching
- [ ] Performance optimization (quantization, GPU delegation)
- [ ] Material 3 UI enhancements

---

## 🤝 Contributing

Contributions are welcome and appreciated!

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/your-feature-name`
3. **Commit** your changes: `git commit -m 'Add some feature'`
4. **Push** to the branch: `git push origin feature/your-feature-name`
5. **Open** a Pull Request

---

## 📄 License

This project is intended for **educational and research purposes**.

Please ensure compliance with the licenses of:
- [Stable Diffusion](https://huggingface.co/spaces/CompVis/stable-diffusion-license) models
- [ONNX Runtime](https://github.com/microsoft/onnxruntime/blob/main/LICENSE)

---

## 👨‍💻 Author

**Mohith Shuka**

[![GitHub](https://img.shields.io/badge/GitHub-@mohithshuka-181717?style=flat-square&logo=github)](https://github.com/mohithshuka)

---

<div align="center">

If you found this project useful, please consider giving it a ⭐ on GitHub — it helps a lot!

</div>
