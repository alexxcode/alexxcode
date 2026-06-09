# Alexis Rojas

**Applied AI Engineer. Computer vision systems that run in production.**

I build end-to-end vision systems: from dataset construction and model training to real-time inference on edge devices and cloud deployment. Most of my recent work comes from an EU-funded industrial R&D program (CDTI/EUREKA) where I designed and shipped the core ML infrastructure for a smart manufacturing platform, and from independent systems in identity verification and geospatial analysis.

I care about the part of ML that usually fails: getting models to work reliably outside the notebook.

---

## Selected systems

### Vivace — Passive Liveness Detection (PAD)
End-to-end Presentation Attack Detection system for KYC identity verification: given face frames from a camera, it classifies live subjects vs. 2D spoofing artifacts (print and screen replay). Covers the full lifecycle: subject-disjoint data pipeline (TFRecords on GCS), EfficientNetB0 training with focal loss, ISO/IEC 30107-3 evaluation (APCER / BPCER / ACER, DET curves, oracle-gap diagnostics), versioned model bundles, and FastAPI serving on Cloud Run with strict train/serve preprocessing parity. The evaluation harness caught the model's own generalization failure (an image-quality shortcut learned from the dataset) before deployment, which is exactly what a PAD evaluation protocol exists to do. 123 tests across preprocessing, data, training, evaluation, and serving. No image retention, non-PII logging.
**Stack:** TensorFlow/Keras (EfficientNetB0), MediaPipe, OpenCV, tf.data/TFRecords, FastAPI, Docker, Cloud Run, Cloud Build, GCS, pytest.


### Palimpsest — Satellite Change Detection
Detects structural change between Sentinel-2 image pairs using a ChangeFormer model I trained from scratch on LEVIR-CD (F1 = 0.8169) and fine-tuned on OSCD. Served via FastAPI on Cloud Run, results stored in BigQuery, with an LLM agent layer for natural-language querying over detections.
**Stack:** PyTorch, ChangeFormer, Sentinel-2, FastAPI, Cloud Run, BigQuery, Gemini function calling.

### MENTAT — SAM 2 Pre-labeling Service
Microservice that automates video annotation for industrial datasets using SAM 2 propagation. Reduced manual annotation time by ~94% across 115,000+ frames, feeding the training pipeline for eight production use cases.
**Stack:** SAM 2, FastAPI, Celery, Redis, Docker.
*Built under an EU-funded R&D project. Code private.*

### Fábrica de Modelos — Industrial MLOps Platform
Training, model registry, and hot-swap inference platform for industrial vision models. Handles dataset versioning, training jobs, evaluation, and zero-downtime model replacement on edge devices.
**Stack:** Python, FastAPI, Docker, GCP, YOLO11, TensorRT.
*Built under an EU-funded R&D project. Code private.*

### EXPAI Inference Platform — Multi-agent Edge Inference
Real-time, multi-camera inference system running eight concurrent computer vision use cases (PPE compliance, assembly verification, dimensional metrology, surface defect detection, object counting with ByteTrack) on NVIDIA Jetson.
**Stack:** NVIDIA Jetson, TensorRT, YOLO11, Python, Redis.
*Built under an EU-funded R&D project. Code private.*

---

## What I work with

**Core:** Python, FastAPI, Redis, Celery, Docker
**Vision / ML:** PyTorch, TensorFlow/Keras, YOLO11, SAM 2, OpenCV, MediaPipe, TensorRT, transformer-based change detection
**Cloud / Data:** GCP (Cloud Run, BigQuery, Vertex AI, Cloud Build, GCS), dbt, tf.data/TFRecords
**Edge:** NVIDIA Jetson deployment and optimization
**Practices:** train/serve parity by construction, versioned model bundles, subject-disjoint evaluation protocols, pytest test suites
**Also:** synthetic data generation (Blender, NVIDIA Isaac Sim), SQL, C++

**Languages:** Spanish (native), English (C1)

---

## Contact

- Email: alexisrrm12@gmail.com
- LinkedIn: [linkedin.com/in/alexis-rojas-alexxcode](https://www.linkedin.com/in/alexis-rojas-alexxcode/)

Open to Applied AI / Computer Vision roles, remote or relocation.
