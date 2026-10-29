<div align="center">

# 🌿 TerraLeaf-AI

**Plant disease classification with a dedicated deep-learning model for each of 10 crops.**

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?logo=tensorflow&logoColor=white)
![Flask](https://img.shields.io/badge/API-Flask-000000?logo=flask&logoColor=white)
![Crops](https://img.shields.io/badge/Crops-10-2ea44f)

</div>

---

## 🔍 Overview

TerraLeaf-AI diagnoses leaf diseases across **10 plant species**. Instead of one big model, each plant has its **own specialized CNN**, trained on that crop's diseases (3 to 10 classes per plant, including a *healthy* class). The aim is to give farmers, botanists and agronomists a fast, accurate first diagnosis.

## 🌍 Why it matters

Plant diseases can devastate yields and food security. Catching them early helps to:

- Minimize crop losses
- Enable precise disease management
- Reduce unnecessary chemical treatment, supporting sustainable agriculture

## ✨ Key features

- **Multi-model design:** one dedicated model per plant, tuned to its own diseases
- **Simple prediction API:** send a leaf image and the plant type, get a diagnosis and a confidence score
- **Scalable:** new plants or diseases can be added as separate models
- **Data augmentation** to improve generalization on unseen images

## 🌱 Supported plants and performance

| Plant | Classes | Accuracy | Precision | Recall | F1 | Detects |
|---|:--:|:--:|:--:|:--:|:--:|---|
| Apple | 7 | 98.19% | 98.2% | 98.19% | 98.18% | alternaria leaf spot, black rot, brown spot, gray spot, rust, scab, healthy |
| Banana | 7 | 94% | 94% | 94% | 94% | bract mosaic virus, fungal infection, insect damage, Moko, Panama, Sigatoka, healthy |
| Beans | 3 | 91.4% | 91.5% | 91.4% | 91.4% | angular leaf spot, bean rust, healthy |
| Cassava | 5 | 85% | 85% | 85% | 85% | bacterial blight, brown streak, green mottle, mosaic, healthy |
| Grape | 4 | 98.66% | 98.68% | 98.66% | 98.65% | black rot, Esca (black measles), leaf blight, healthy |
| Groundnut | 5 | 86% | 86% | 86% | 86% | early leaf spot, late leaf spot, rust, nutrition deficiency, healthy |
| Maize (Corn) | 4 | 93.75% | 93.93% | 93.75% | 93.81% | gray leaf spot, common rust, northern leaf blight, healthy |
| Tomato | 10 | 94% | 94.7% | 94% | 94.19% | bacterial spot, early blight, late blight, leaf mold, Septoria, spider mites, target spot, yellow leaf curl virus, mosaic virus, healthy |
| Potato | 3 | 97.6% | 97.7% | 97.6% | 97.6% | early blight, late blight, healthy |
| Rice | 4 | 81.25% | 81.8% | 81.25% | 81% | brown spot, leaf blast, hispa, healthy |

## 🧠 Model architecture

Each model is a **convolutional neural network (CNN)** built in TensorFlow for image classification, trained on public datasets with data augmentation to generalize to unseen images.

<!-- TODO (optional): add dataset sizes, number of layers and image size per model if you want to document them -->

## 🚀 Quick start

```bash
git clone https://github.com/Emdysuji/TerraLeaf-AI.git
cd TerraLeaf-AI

python -m venv .venv
# Windows: .venv\Scripts\activate    |    Linux/macOS: source .venv/bin/activate

pip install -r requirements.txt
```

<!-- TODO: requirements.txt was not in the repo file list. Add it, or replace the line above with: pip install flask tensorflow pillow numpy -->

### Run the API

```bash
python API/api.py
```

<!-- TODO: confirm the real path/name of the API script inside the API folder -->

By default it runs at `http://127.0.0.1:5000/`.

### Make a prediction

Send a `POST` request to `/predict` with form data:

| Field | Description |
|---|---|
| `plant` | Plant type, e.g. `apple`, `banana`, `tomato` |
| `file` | The leaf image |

```bash
curl -X POST "http://127.0.0.1:5000/predict" \
     -F "plant=apple" \
     -F "file=@path/to/image.jpg"
```

**Example response**

```json
{
  "plant": "apple",
  "predictions": "Apple___black_rot",
  "confidence": 0.95
}
```

**Errors** are returned as JSON:

```json
{"error": "Invalid plant type. Available options: [list of plants]"}
{"error": "No file provided."}
{"error": "Error details..."}
```

## 🐳 Deployment

Run with gunicorn:

```bash
gunicorn -w 4 -b 0.0.0.0:5000 api:app
```

Or with Docker:

```dockerfile
FROM python:3.9
WORKDIR /app
COPY . .
RUN pip install flask tensorflow pillow numpy
CMD ["python", "api.py"]
```

## 📚 Dataset sources

| Plant | Source |
|---|---|
| Apple, Cassava | [Plant Diseases Training Dataset](https://www.kaggle.com/datasets/nirmalsankalana/plant-diseases-training-dataset) |
| Banana | [Banana Disease Recognition Dataset](https://www.kaggle.com/datasets/sujaykapadnis/banana-disease-recognition-dataset), [BananaLSD](https://www.kaggle.com/datasets/armaanoajay/bananalsd) |
| Beans | [Bean Disease Dataset](https://www.kaggle.com/datasets/therealoise/bean-disease-dataset) |
| Grape, Maize, Tomato, Potato | [PlantVillage Dataset](https://www.kaggle.com/datasets/abdallahalidev/plantvillage-dataset) |
| Groundnut | [Groundnut Plant Leaf Data](https://www.kaggle.com/datasets/warcoder/groundnut-plant-leaf-data) |
| Rice | [Rice Leaf Images](https://www.kaggle.com/datasets/nizorogbezuode/rice-leaf-images) |

## 👤 Author

**Michael-David Osuji**, AI Engineer · Nigeria
[LinkedIn](https://www.linkedin.com/in/michael-david-osuji) · [GitHub](https://github.com/Emdysuji)

<div align="center">

⭐ If you like this project, give it a star and share it.

</div>
