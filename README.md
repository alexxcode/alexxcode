# Alexis Rojas

**Production Machine Learning Engineer · MLOps & Applied AI**

I build and operate ML systems end to end: data pipelines, cloud/edge infrastructure, and out-of-sample evaluation that holds up in production. Every metric I publish is the deployable one, not the optimistic diagnostic.

Former **Lead AI Engineer** at an industrial AI company in Spain, where I led a team of three taking computer vision and MLOps infrastructure into production for an EU-funded smart manufacturing program (EUREKA / CDTI).

**Open to:** Senior/Mid ML Engineer & MLOps roles · Remote (EU / Global, full-time or B2B contract)  
[Email](mailto:alexisrrm12@gmail.com) · [LinkedIn](https://www.linkedin.com/in/alexis-rojas-alexxcode/)

---

## Production Track Record

- **MLOps Platform:** Built an end-to-end model lifecycle—dataset versioning, on-demand L4 GPU training with automatic shutdown, atomic model promotion via GCS conditional writes, and zero-downtime hot-swaps to edge devices.
- **Edge AI at Scale:** Deployed 8 concurrent computer vision use cases (PPE compliance, operator inactivity, kitting, assembly verification) on NVIDIA Jetson with TensorRT in a Madrid tool-and-die plant.
- **Data Engine (MENTAT):** Built a SAM 2 pre-labeling microservice that cut manual annotation time by ~94% across 115,000+ frames.

---

## Selected Systems

### MLOps & Production Infrastructure

- **[AlphaPlus](https://github.com/alexxcode/fabrica-de-modelos)** — *End-to-End Model Factory*  
  Dataset ingestion, on-demand GPU training (auto-shutdown post-run), atomic registry promotion (GCS conditional writes), and validation API. Shipped models at 95.5% and 92.6% mAP@50.  
  `FastAPI` `React` `PostgreSQL` `Celery` `GCP` `YOLO11`

- **[EXPAI Inference Platform](https://github.com/alexxcode/expai-inference-platform)** — *Real-Time Industrial Video Analytics*  
  Modular inference engine with a shared core (YOLO11, ByteTrack, decoding/rendering) and pluggable modules for PPE, inactivity, metrology, and kitting. Runs at ~26.6 FPS on a T4.  
  `PyTorch` `TensorRT` `NVIDIA Jetson` `FastAPI` `Docker`

- **[Aleph](https://github.com/alexxcode/aleph)** — *Analytics & Demand Forecasting Platform*  
  Warehouse architecture (Kimball, SCD2, data contracts, keyless CI) feeding a LightGBM demand forecast (WAPE ~0.11) back into BigQuery as automated reorder recommendations.  
  `dbt` `BigQuery` `LightGBM` `GitHub Actions`

### Applied AI, LLMs & Rigorous Evaluation

- **[The Catcher in the RAG](https://github.com/alexxcode/the-catcher-in-the-rag)**  — *Auditable Accounts Payable Agent*  
  Verifies invoices against contracts: every finding cites the clause verbatim or is dropped; abstains when no relevant clause exists. Out-of-sample on CUAD: 85.9% Hit@5 (vs. 68.6% BM25) and correct abstention raised from 27.9% to 63.3%.  
  `LangGraph` `Vertex AI (Gemini)` `Langfuse` `Terraform` `Cloud Run`

- **[Vivace](https://github.com/alexxcode/liveness-pad)** · **[Live Demo](https://liveness-api-6pxuzbuieq-uc.a.run.app/)** — *Passive Liveness Detection for KYC*  
  Evaluated against ISO/IEC 30107-3 with shared train/serve preprocessing to eliminate skew by construction. Caught a sharpness shortcut pre-deployment and reports deployable ACER (13.06%) vs. oracle (2.76%).  
  `PyTorch` `FastAPI` `Cloud Run`

- **[Dupin](https://github.com/alexxcode/dupin)** — *Real-Time Fraud Scoring & Leakage Audit*  
  15–20 ms scoring API on PaySim demonstrating the gap between naive leakage (99.8% recall) and honest temporal deployment (35.3% recall at 75.4% precision, plus a zero-FP auto-block tier).  
  `LightGBM` `FastAPI`

- **[Palimpsest](https://github.com/alexxcode/palimpsest)** — *Geospatial Change Detection*  
  Sentinel-2 pipeline via Earth Engine, Siamese change detection (F1 0.86 on LEVIR-CD) adapted across a 20x resolution gap, GeoJSON polygons in BigQuery, and a Gemini agent explaining changes.  
  `Google Earth Engine` `PyTorch` `BigQuery` `Gemini`

---

## Engineering Principles

1. **Deployable metrics only:** Thresholds are fixed on validation and reported on unseen data. Optimistic numbers are explicitly labeled as diagnostics.
2. **Train/serve parity by construction:** One preprocessing path and one source of truth for data.
3. **Cost and failure as first-class inputs:** GPUs that shut themselves off, atomic promotions, and systems that abstain instead of guessing.

---

## Core Stack

- **MLOps & Cloud:** GCP (Vertex AI, Cloud Run, BigQuery, GCS, Compute Engine), Terraform, Docker, GitHub Actions, pytest, dbt
- **ML & Vision:** PyTorch, YOLO11, SAM 2, TensorRT, NVIDIA Jetson, OpenCV, LightGBM, TensorFlow/Keras
- **LLMs & Agents:** LangGraph, Gemini, Hybrid Retrieval (BM25 + embeddings), Langfuse
- **Backend & Data:** Python, SQL, FastAPI, Celery, Redis, PostgreSQL

**Languages:** Spanish (native) · English (C1)
