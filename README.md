# Alexis Rojas

**AI Engineer. LLM agents, RAG and ML systems in production — and the evaluation that proves they work.**

I build AI systems for finance and compliance workflows: audit agents, contract RAG, fraud scoring and identity verification. My focus is the part that doesn't demo well: measuring accuracy honestly, knowing when a system should refuse to answer, and tracing every decision it makes.

That discipline comes from shipping ML where failure is visible: as Lead AI Engineer on a European industrial AI platform, I built the model registry and hot-swap inference behind eight models running concurrently on factory edge hardware. The same rules carry over to LLMs — versioned, traced, evaluated on data the system has never seen.

---

## Featured

### [The Catcher in the RAG](https://github.com/alexxcode/the-catcher-in-the-rag) — LLM audit agent + contract RAG
An accounts-payable agent that stands between the invoice and the payment. It runs a three-way match (PO, goods receipt, invoice), retrieves the governing contract clauses, and returns `APPROVE` / `REVIEW` / `REJECT` / `ABSTAIN`.

- **Cite or stay quiet.** Every clause-backed finding carries a verbatim quote validated as an exact substring of the contract, with character offsets. No valid quote, no finding.
- **Bartleby, the abstention guard.** When no clause is relevant enough, the agent declines to judge and hands the package to a human.
- **The LLM extracts; a deterministic policy engine decides.** LangGraph state machine, Gemini on Vertex AI, full Langfuse tracing.
- **Measured on real SEC contracts (CUAD), out of sample:** dense retrieval reaches 85.9% Hit@5 vs. 68.6% for BM25. LLM verification raises correct abstention on absent clauses from 27.9% to 63.3%.
- **Honest limits, published:** false abstentions are still 47.4% of present clauses, and the retrieval score alone barely beats chance at separating them. Every number in the README is regenerated from eval reports, with confidence intervals.

**Stack:** Python, LangGraph, Vertex AI (Gemini, `text-embedding-005`), BM25 + dense hybrid retrieval, Langfuse, FastAPI, Streamlit, Terraform, Cloud Run.
[Live demo](https://catcher-ui-staging-hrok623gcq-uc.a.run.app) (stub mode, may be scaled to zero)

### [Dupin](https://github.com/alexxcode/dupin) — Real-time transaction fraud scoring
A raw transaction in; a risk score, an `approve` / `review` / `block` decision and a human-readable reason per flag out, with latency measured under load. Temporal splits and a leakage audit so the headline metric is the deployable one, not the optimistic one. Live monitoring dashboard on Cloud Run.
**Stack:** LightGBM, FastAPI, Docker, Cloud Run, Cloud Build.
*Trained on synthetic data (PaySim): the contribution is the methodology and the system, not production-grade metrics.*

### Vivace — Passive liveness detection for KYC
Presentation Attack Detection (live face vs. print or screen replay) evaluated against ISO/IEC 30107-3 (APCER / BPCER / ACER). Thresholds chosen on validation and reported on held-out data, not oracle-tuned; cross-dataset generalization as the truth criterion. Train/serve preprocessing parity enforced by construction, 123 tests, no image retention.
**Stack:** TensorFlow/Keras (EfficientNetB0), MediaPipe, FastAPI, Cloud Run.

---

## In production (industrial AI platform, code private)

- **MLOps platform ("model factory"):** dataset versioning, training jobs, model registry and zero-downtime hot-swap inference on edge devices.
- **MENTAT — SAM 2 pre-labeling service:** ~94% less manual annotation time across 115,000+ frames.
- **Edge inference:** eight concurrent vision use cases (PPE compliance, assembly verification, defect detection, counting) on NVIDIA Jetson with TensorRT.

## More projects

- [**Aleph**](https://github.com/alexxcode/aleph) — demand forecasting on dbt + BigQuery + LightGBM; WAPE ~0.11 at one-week horizon.
- [**Palimpsest**](https://github.com/alexxcode/palimpsest) — satellite change detection (ChangeFormer, F1 0.817 on LEVIR-CD) with an LLM function-calling layer over BigQuery.

---

## What I work with

**LLM / agents:** LangGraph, Vertex AI (Gemini), hybrid retrieval (BM25 + embeddings), abstention and citation validation, Langfuse, eval harnesses with confidence intervals
**ML:** PyTorch, TensorFlow/Keras, LightGBM, YOLO11, SAM 2
**Engineering:** Python, FastAPI, Docker, Redis, Celery, pytest
**Cloud / data:** GCP (Cloud Run, Vertex AI, BigQuery, GCS, Cloud Build), Terraform, dbt
**Edge:** NVIDIA Jetson, TensorRT

**Languages:** Spanish (native), English (C1)

---

## Contact

- Email: alexisrrm12@gmail.com
- LinkedIn: [linkedin.com/in/alexis-rojas-alexxcode](https://www.linkedin.com/in/alexis-rojas-alexxcode/)

Open to AI Engineer / LLM Engineer roles — remote, full-time or contract. 
