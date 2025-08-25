# Shoe Generator - Stable Diffusion v1.5 LoRA Finetuned

A web application for generating realistic shoe images using a finetuned Stable Diffusion v1.5 model with LoRA adapters. The model is specialized in creating high-quality images of sneakers, boots, sandals, and other footwear.

## 🚀 Live Demo

**Try it online:** [Shoe Generator on Hugging Face Spaces](https://huggingface.co/spaces/Shoe-Gen/Shoe_Generator_Hosting)

The live demo is hosted on Hugging Face Spaces and runs on CPU (may be slower but accessible to everyone).

## 📖 About

This project implements a Gradio-based web interface for a Stable Diffusion model that has been finetuned on the UT Zappos50K Shoes Dataset using LoRA (Low-Rank Adaptation). The model excels at generating realistic shoe images from text descriptions.

**Key Features:**
- Finetuned Stable Diffusion v1.5 with LoRA adapters
- Specialized in footwear generation (sneakers, boots, sandals, etc.)
- User-friendly Gradio web interface
- Customizable inference parameters
- Local and cloud deployment options

## 🛠️ Installation & Setup

### Prerequisites
- Python 3.8 or higher
- Git
- GPU recommended (CUDA support) for faster inference

### Clone the Repository
```bash
git clone https://github.com/benisonjac/Shoe_Generator_Hosting.git
cd shoe-generator
```

### Install Dependencies
```bash
# Create virtual environment (recommended)
python -m venv shoe-env
source shoe-env/bin/activate  # On Windows: shoe-env\Scripts\activate

# Install required packages
pip install -r requirements.txt
```

### Download the Model
The model will be automatically downloaded from Hugging Face Hub when you first run the application, or you can pre-download it:

```python
from huggingface_hub import snapshot_download
snapshot_download(repo_id="benisonjac/stable-diffusion-finetune", local_dir="./models")
```

## 🏃‍♂️ Running the Application

### Local Development
```bash
python app.py
```

The application will start on `http://localhost:7860` by default.

### Configuration Options
You can customize the application by modifying the parameters in `app.py`:

```python
# Model parameters
MODEL_ID = "your-username/shoe-generator"
DEVICE = "cuda" if torch.cuda.is_available() else "cpu"

# Gradio interface settings
PORT = 7860
SERVER_NAME = "0.0.0.0"  # Change for network access
```

### Running with Custom Settings
```bash
# Run on different port
python app.py --port 8080

# Run with CPU only
python app.py --device cpu

# Run with debug mode
python app.py --debug
```

## 📁 Project Structure

```
shoe-generator/
├── app.py                 # Main Gradio application
├── requirements.txt       # Python dependencies
├── README.md
```

## 💡 Usage Examples

### Basic Usage
```python
from model_utils import ShoeGenerator

generator = ShoeGenerator()
image = generator.generate("a photo of red high-top sneakers")
image.save("output.png")
```

### Advanced Usage with Parameters
```python
image = generator.generate(
    prompt="futuristic white running shoes with neon accents",
    negative_prompt="blurry, low quality, deformed",
    num_inference_steps=50,
    guidance_scale=7.5,
    width=512,
    height=512
)
```

## 🎯 Example Prompts

- `"a photo of black leather boots with metal buckles"`
- `"white canvas sneakers with blue stripes, side view"`
- `"elegant high-heel sandals with gold accents"`
- `"hiking boots with laces, outdoor photography style"`
- `"futuristic running shoes with LED lights"`

## 🚀 Deployment

### Deploy to Hugging Face Spaces
1. Create a new Space on [Hugging Face Spaces](https://huggingface.co/new-space)
2. Upload your files or connect your GitHub repository
3. Set the SDK to "Gradio" 
4. The Space will automatically build and deploy

### Deploy with Docker
```bash
# Build Docker image
docker build -t shoe-generator .

# Run container
docker run -p 7860:7860 shoe-generator
```

## 🔧 Model Details

- **Base Model**: Stable Diffusion v1.5
- **Finetuning Method**: LoRA (Low-Rank Adaptation)
- **Dataset**: UT Zappos50K Shoes Dataset
- **Training**: Specialized on footwear images
- **Model Size**: ~2GB (with LoRA adapters)

## 📋 Requirements

See `requirements.txt` for full dependencies. Key packages include:

```
torch>=1.13.0
diffusers>=0.21.0
transformers>=4.25.0
gradio>=3.50.0
accelerate>=0.20.0
huggingface-hub>=0.16.0
pillow>=9.0.0
```

## 🚨 Limitations

- Works best with shoe-specific prompts
- May not generalize well to other object types
- CPU inference is significantly slower than GPU
- Generated images are 512x512 pixels by default

## 📄 License

- **Code**: MIT License
- **Model**: CreativeML Open RAIL-M (following base Stable Diffusion license)
- **Dataset**: UT Zappos50K (research use only)

This project is intended for research and educational purposes.

## 🙏 Acknowledgements

- [CompVis](https://github.com/CompVis/stable-diffusion) and [RunwayML](https://huggingface.co/runwayml) for Stable Diffusion
- [UT Austin](http://vision.cs.utexas.edu/) for the Zappos50K dataset
- [Hugging Face](https://huggingface.co/) for hosting and tools
- [Gradio](https://gradio.app/) for the web interface

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## 📞 Contact

If you have questions or issues, please open an issue on this repository or contact [your-email@domain.com].

---

⭐ If you find this project useful, please consider giving it a star!
