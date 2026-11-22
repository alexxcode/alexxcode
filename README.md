# Alexis Rojas

**Machine Learning Engineer · Computer Vision & MLOps**

I build ML systems end to end: the data pipeline that feeds the model, the infrastructure that serves it, and the evaluation that tells you whether to trust it. Every number I publish is the one that survives deployment, not the optimistic one.

Former **Lead AI Engineer** at an industrial AI company in Spain, where I led a team of three and took computer vision into production for a smart manufacturing program funded by the EU (EUREKA / CDTI).

---

## In production

- **Edge vision on the factory floor.** Eight vision use cases (PPE compliance, operator inactivity, kitting, assembly verification) running concurrently on NVIDIA Jetson with TensorRT in a tool and die plant in Madrid.
- **MLOps platform.** Dataset versioning, training on GPU machines that switch themselves off when done, a model registry with atomic promotion, and model swaps on edge devices without downtime.
- **MENTAT.** A SAM 2 pre-labeling service: about 94% less manual annotation time across 115,000+ frames.

---

## Featured work

### Computer vision

**[EXPAI Inference Platform](https://github.com/alexxcode/expai-inference-platform)**
Modular real time video analytics for industrial plants. A shared core (YOLO11, ByteTrack, video decoding, rendering) plus one module per use case: PPE, inactivity, metrology, kitting, process monitoring. FastAPI, Docker, about 26.6 FPS on a T4.

**[AlphaPlus](https://github.com/alexxcode/fabrica-de-modelos)**
The model factory behind it. Dataset ingestion, YOLO training on an on demand L4 GPU that shuts itself down after every run, a registry with atomic promotion through GCS conditional writes, and a validation API. Models shipped at 95.5% and 92.6% mAP@50. FastAPI, React, PostgreSQL, Celery.

**[Vivace](https://github.com/alexxcode/liveness-pad)** · [live demo](https://liveness-api-6pxuzbuieq-uc.a.run.app/)
Passive liveness detection for KYC, evaluated against ISO/IEC 30107-3. Training and serving share one preprocessing module, so train/serve skew is impossible by construction. The evaluation caught the model's own shortcut (image sharpness as a proxy for "live") before deployment, and the README reports the deployable ACER (13.06%), not the oracle one (2.76%).

**[Palimpsest](https://github.com/alexxcode/palimpsest)**
Satellite change detection on Sentinel-2: Earth Engine retrieval, a Siamese change detection model (F1 0.86 on LEVIR-CD) adapted to close a 20x resolution gap, GeoJSON polygons in BigQuery, and a Gemini agent that explains what changed.

### Evaluation and decision systems

**[Dupin](https://github.com/alexxcode/dupin)**
Real time fraud scoring (LightGBM, FastAPI, about 15 to 20 ms per transaction). The point is the gap: a naive 99.8% recall breaks down into label leakage and temporal leakage, and the deployable result is 35.3% recall at 75.4% precision, plus an auto block tier with zero false positives. Synthetic data (PaySim): the contribution is the method, not the absolute number.

### LLM systems

**[The Catcher in the RAG](https://github.com/alexxcode/the-catcher-in-the-rag)** · [live demo](https://catcher-ui-staging-hrok623gcq-uc.a.run.app)
An accounts payable agent that stands between the invoice and the payment. LangGraph, Gemini on Vertex AI, Langfuse, Terraform, Cloud Run. Every finding cites the contract verbatim or is dropped; with no relevant clause, it declines to judge. Out of sample on CUAD: dense retrieval reaches 85.9% Hit@5 vs 68.6% for BM25, correct abstention rises from 27.9% to 63.3%, and the README publishes where it still fails.

### Data platforms

**[Aleph](https://github.com/alexxcode/aleph)**
A dbt and BigQuery platform (Kimball, SCD2, data contracts, keyless CI) that feeds a LightGBM demand forecast (WAPE about 0.11) back into the warehouse as reorder recommendations.

---

## How I work

1. **The deployable metric is the result.** Thresholds are chosen on validation and reported on data the model never saw. Optimistic numbers are labeled as diagnostics.
2. **Parity by construction.** One preprocessing path for training and serving, one source of truth for data.
3. **Cost and failure are design inputs.** GPUs that turn themselves off, promotions that either fully happen or not at all, systems that abstain instead of guessing.

---

## Stack

**Vision and ML:** PyTorch, TensorFlow/Keras, YOLO11, SAM 2, TensorRT, NVIDIA Jetson, OpenCV, LightGBM
**MLOps and engineering:** Python, FastAPI, Docker, Celery, Redis, PostgreSQL, pytest, GitHub Actions
**Cloud and data:** GCP (Vertex AI, Cloud Run, BigQuery, GCS, Compute Engine), Terraform, dbt
**LLM:** LangGraph, Gemini, hybrid retrieval (BM25 + embeddings), Langfuse

**Languages:** Spanish (native), English (C1)

---

## Contact

alexisrrm12@gmail.com · [LinkedIn](https://www.linkedin.com/in/alexis-rojas-alexxcode/)

Open to Machine Learning, Computer Vision and MLOps Engineer roles. Remote, full time or contract.
