### Hi, I'm Bikram 👋

M.Tech CSE student at **IIIT Delhi**. I build **systems and AI infrastructure from the bottom
up**: query engines, vector search, container runtimes and networking, and the LLM applications
on top. My main projects are tested in CI and measured against the established system they
imitate: DuckDB, hnswlib, FAISS, Flannel and runc.

**Systems**

| Project | What it is | Stack |
|---|---|---|
| [**morsel**](https://github.com/vik-bit/morsel) | Vectorized, columnar query engine: AVX2 kernels with runtime CPU dispatch, hash joins and aggregation, morsel-driven parallelism. **8 TPC-H queries give exactly DuckDB's answers** at SF 1, and the engine is benchmarked against DuckDB, with the caveats stated | C++17 · SIMD · sanitizers |
| [**vecdex**](https://github.com/vik-bit/vecdex) | HNSW vector search engine from scratch, with SIMD distance kernels and parallel graph construction. **Same recall as hnswlib and FAISS on SIFT1M** (0.999 recall@10). Its benchmarks exposed a race in parallel builds, fixed and checked with ThreadSanitizer | C++17 · AVX2 / NEON · pybind11 |
| [**minirun**](https://github.com/vik-bit/minirun) | Container runtime and Kubernetes CNI plugin on raw Linux primitives: namespaces, cgroups v2, a hand-assembled seccomp filter, veth and bridges. **The only CNI of a 3-node cluster, matching Flannel in the same routing mode** (24 Gbit/s pod to pod) | Go · Linux · Kubernetes |

**AI systems**

| Project | What it is | Stack |
|---|---|---|
| [**PolicyPilot**](https://github.com/vik-bit/policypilot) | Agentic RAG that maps new regulations to the policy clauses they affect, drafts the changes and verifies every quote. The agent beats a no-AI baseline (100% vs 85% precision, 96% vs 50% impact labels; **McNemar p = 0.0002**), with a pre-registered evaluation, a held-out set of real Indian regulations and prompt-injection tests | Python · LLM agents · hybrid search · FastAPI |
| [**MLOps Platform**](https://github.com/vik-bit/mlops-platform) · [live](https://mlops-frontend-5smr.onrender.com/) | Train, deploy and monitor ML models, with experiment tracking, drift detection and an LLM copilot that answers from live platform data | Python · MLflow · Docker · TypeScript |

**Data**

| Project | What it is | Stack |
|---|---|---|
| [**Kafka Stream Analytics**](https://github.com/vik-bit/kafka-taxi-stream-analytics) | Replays NYC taxi trips through Kafka and checks streaming sketches (Bloom, HyperLogLog, DGIM, MinHash-LSH) against exact answers as partitions, keys and producer speed change | Python · Kafka |
| [**Spark vs MapReduce vs DuckDB**](https://github.com/vik-bit/nyc-taxi-mapreduce-spark-duckdb) | The same analytics workloads on three engines, with measured timings | Python · Spark · DuckDB |
| [**Kubernetes CNI benchmarks**](https://github.com/vik-bit/GROUP6_GRSPROJECT) | Led a team of 5 benchmarking Flannel, Calico and Cilium on Kind and bare-metal clusters | Kubernetes · Python |

**Also:** Tech lead on [RecipeDB 3.0](https://cosylab.iiitd.edu.in/recipedb3) (IIIT Delhi research) · frontend intern at
Be10x AI (a code editor used by 600K+ learners) · Codeforces [1563](https://codeforces.com/profile/BikiByte)

**Tools:** C++17 · Go · Python · TypeScript · SIMD (AVX2, NEON) · Linux internals · Docker · Kubernetes · FastAPI · MLflow · Kafka · Spark · PostgreSQL · AWS
