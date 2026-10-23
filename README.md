### Hi, I'm Bikram 👋

M.Tech CSE student at **IIIT Delhi**. I build **AI and ML systems end to end**: the retrieval engine
in C++, the LLM agents on top of it, the infrastructure that serves them, and the evaluations that
prove they work.

**Featured projects**

| Project | What it is | Stack |
|---|---|---|
| [**vecdex**](https://github.com/vik-bit/vecdex) | HNSW vector search engine written from scratch: SIMD distance kernels, parallel graph construction, Python bindings. Same recall as hnswlib and FAISS on SIFT1M (0.999 recall@10). Benchmarks exposed a race in parallel builds that doubled unreachable nodes; found, fixed and verified with ThreadSanitizer | C++17 · AVX2 / NEON · pybind11 · CMake |
| [**PolicyPilot**](https://github.com/vik-bit/policypilot) | Agentic RAG that maps new regulations to the policy clauses they affect, drafts changes, and verifies every quote. 96% retrieval recall@3; the AI agent reaches 100% precision and 96% impact accuracy against 85% / 50% for a no-AI baseline. Can use vecdex for its vector search | Python · LLM agents (Claude / Groq) · hybrid search · FastAPI |
| [**MLOps Platform**](https://github.com/vik-bit/mlops-platform) · [live](https://mlops-frontend-5smr.onrender.com/) | Train, deploy and monitor ML models, with experiment tracking, drift detection and an LLM copilot | Python · MLflow · Docker · TypeScript |
| [**Kubernetes CNI benchmarks**](https://github.com/vik-bit/GROUP6_GRSPROJECT) | Led a team of 5 benchmarking Flannel, Calico and Cilium networking on Kind and bare-metal kubeadm clusters | Kubernetes · Python |
| [**Kafka Stream Analytics**](https://github.com/vik-bit/kafka-taxi-stream-analytics) | Replays NYC taxi trips through Kafka and checks streaming sketches (Bloom, HyperLogLog, DGIM, MinHash-LSH) against exact answers | Python · Kafka |
| [**Spark vs MapReduce vs DuckDB**](https://github.com/vik-bit/nyc-taxi-mapreduce-spark-duckdb) | The same analytics workloads on three engines, with measured timings | Python · Spark · DuckDB |

**Also:** Tech lead on [RecipeDB 3.0](https://cosylab.iiitd.edu.in/recipedb3) (IIIT Delhi research) · frontend intern at
Be10x AI (a code editor used by 600K+ learners) · Codeforces [1563](https://codeforces.com/profile/BikiByte)

**Tools:** Python · C/C++ · SIMD (AVX2, NEON) · TypeScript · FastAPI · Next.js · Docker · Kubernetes · MLflow · Kafka · Spark · PostgreSQL · AWS
