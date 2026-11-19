### SpotHole — Automated Pothole Detection (`README.md`)

# SpotHole — Automated Pothole Detection System

SpotHole is a real-time computer vision system for detecting road potholes and surface anomalies from images. Built on **YOLOv8**, it pairs low-latency object detection with a **FastAPI** inference service and **Supabase** cloud logging for scalable road condition monitoring.

## Key Features

* **Real-Time Pothole Detection:** Uses a custom-trained **YOLOv8** model to detect and localize road potholes with bounding boxes and confidence scores across live video feeds and recorded footage.
* **Optimized Inference Pipeline:** Streamlined frame preprocessing and post-processing with OpenCV and PyTorch for responsive frame rates.
* **REST API Backend:** Exposes clean **FastAPI** endpoints for image/video inference and automated alert generation.
* **Cloud Persistence with Supabase:** Logs detection events, timestamps, confidence metrics, and incident records directly to a **Supabase** PostgreSQL database and storage bucket.

## Tech Stack

* **Computer Vision & ML:** Ultralytics YOLOv8, PyTorch, OpenCV
* **Backend & API:** Python, FastAPI, Uvicorn
* **Database & Storage:** Supabase

## Project Structure

```text
├── app/                # FastAPI routes, inference pipeline, and Supabase client integration
├── weights/            # Trained YOLOv8 model weights (best.pt)
├── notebooks/          # Training and evaluation experiments
├── requirements.txt    # Project dependencies
└── .env.example        # Environment variable template
``` 
## Getting Started
### 1. Clone the Repository
```bash
git clone [https://github.com/Nigama-Reddy-V/SpotHole_final.git](https://github.com/Nigama-Reddy-V/SpotHole_final.git)
cd SpotHole_final
```

### 2. Install Dependencies
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Configure Environment Variables
Create a .env file in the root directory and add your Supabase credentials:
```bash
SUPABASE_URL=your_supabase_project_url
SUPABASE_KEY=your_supabase_anon_or_service_key
MODEL_PATH=weights/best.pt
```

### 4. Start the Server
```bash
uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
```
Once running, open http://localhost:8000/docs to test the interactive Swagger API endpoints with sample road images or video streams.
