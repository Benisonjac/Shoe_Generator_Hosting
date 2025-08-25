---
title: Deploy Stable Diffusion Finetuned Model
emoji: 🖼
colorFrom: purple
colorTo: red
sdk: gradio
sdk_version: 5.43.1
app_file: app.py
pinned: false
short_description: Hosting a website for hosting the Shoe Generation
license: mit
---
# 👟 Text-to-Image Shoe Generator

This project uses a fine-tuned Stable Diffusion model to generate unique and high-quality shoe designs from text prompts.

## 🔍 What It Does

-   **Generates Shoe Images**: Creates photorealistic or stylized shoe images based on user descriptions.
-   **Customizable Output**: Allows users to control generation parameters like guidance scale and inference steps.
-   **Fine-Tuned Model**: Built on Stable Diffusion, fine-tuned specifically on a dataset of shoe images for specialized results.
-   **Interactive UI**: Features a simple and intuitive web interface built with Gradio.

---

## Run on Hugging Face Spaces

[![Hugging Face Spaces](https://huggingface.co/spaces/benisonjac/deploy-stable-diffusion-finetuned-model)](https://huggingface.co/spaces/benisonjac/deploy-stable-diffusion-finetuned-model)


---

## Run in Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/RoshanVarghese/TextToImage/blob/main/GenAI_TextToImage_GitHub.ipynb)

---

## Files

-   `app.py`: The main script that runs the Gradio web interface.
-   `requirements.txt`: A list of Python packages required to run the project.
-   **Model**: The fine-tuned model is hosted on the Hugging Face Hub at [roshanVarghese/TextToImageShoe](https://huggingface.co/spaces/benisonjac/deploy-stable-diffusion-finetuned-model).

---

## Local Setup

To run this project on your own machine, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/RoshanVarghese/TextToImageShoe.git](https://github.com/RoshanVarghese/TextToImageShoe.git)
    cd TextToImageShoe
    ```
    *(Note: Replace the URL if your GitHub repository is different.)*

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the application:**
    ```bash
    python app.py
    ```
    This will start a local Gradio server. Open the URL provided in your terminal to use the app.
