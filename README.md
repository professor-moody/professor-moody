# Nathan (`m00dy` / `@professor-moody`)

I am Nathan (`m00dy`), a security researcher and systems engineer focused on **AI/ML runtime security**, **binary format and parser verification**, **weight-space analysis**, and **adversarial tradecraft simulation**.

My work centers on finding memory-safety, type-confusion, and deserialization defects across the native C, C++, and Rust software stack that loads and executes machine learning models and binary containers, alongside building open-source tooling for red-team infrastructure, post-exploitation research, and defensive telemetry validation.

- **Notebook & Writing:** [m00dy.sh](https://m00dy.sh)
- **The Unchecked Atlas:** [unchecked.sh](https://unchecked.sh)
- **GitHub:** [github.com/professor-moody](https://github.com/professor-moody)

---

## Research & Open-Source Projects

### AI/ML Security & Parser Verification
- **[Secant](https://github.com/professor-moody/secant)** ([Docs](https://professor-moody.github.io/secant/)) - Rust and Python toolkit for **Weight-Space Programming (WSP)** covering zero-evaluation spectral weight auditing (`secant inspect` / `read`), multi-subspace Gram-Schmidt composition with closed-form Target-Shift Calibration (`secant compose`), zero-copy `mmap` and `Q8_0` block-aligned surgery (`secant patch` / `quant patch`), and subspace-locked LoRA micro-training (`ProjectThenHealLinear`).
- **[Crucible](https://github.com/professor-moody/crucible)** ([Docs](https://professor-moody.github.io/crucible/)) - Structure-aware grammar and mutation framework for ML model formats (`GGUF`, `ONNX`, `SafeTensors`, `TFLite`, `FlatBuffers`, `Protobuf`) that pairs schema-driven mutators with sanitizer-instrumented harnesses and stack-hash crash deduplication.
- **[The Unchecked Atlas](https://unchecked.sh)** - Interactive vulnerability research atlas mapping parser boundaries, container deserialization hazards, and native runtime memory-safety invariants across modern systems and ML stacks.

### Adversarial Tradecraft, Emulation & Infrastructure
- **[Scorch](https://github.com/professor-moody/Scorch)** (`47★`) & **[ludus_scorch](https://github.com/professor-moody/ludus_scorch)** (`19★`) - Gamified adversary emulation and detection validation range (`Scorch`) and its automated [Ludus](https://docs.ludus.cloud) deployment role for repeatable red/blue cyber exercises.
- **[aipostex](https://github.com/professor-moody/aipostex)** (`6★`) & **[aipostex-lab](https://github.com/professor-moody/aipostex-lab)** - AI/ML post-exploitation tradecraft framework and companion lab environment for researching security boundaries across deployed inference services and model pipelines.
- **[ludus_litterbox_role](https://github.com/professor-moody/ludus_litterbox_role)** (`20★`) - Ansible role for deploying the LitterBox malware analysis and payload testing sandbox into Ludus virtual environments.
- **[Hemlock](https://github.com/professor-moody/Hemlock)** - Modular command-and-control (C2) framework built to study extensible implant communication protocols and operator workflows.
- **[halo-forge](https://github.com/professor-moody/halo-forge)** (`9★`) - Benchmark and reinforcement-learning training framework (`Halo-Forge`) for AMD Strix Halo systems.

---

## Accepted Upstream Contributions & Published Advisories

### Merged Upstream Pull Requests (36 Merged Across 16 Repositories)
- **ML Runtimes, Compilers & Tokenizers:**
  - [`tensorflow/tensorflow`](https://github.com/tensorflow/tensorflow/pulls?q=is%3Apr+author%3Aprofessor-moody+is%3Amerged) (15 merged PRs across `core/framework`, `core/kernels`, `core/grappler`, `core/util/tensor_bundle`, and `core/lib/jpeg`/`webp`: `#129806`, `#129690`, `#129689`, `#129688`, `#129671`, `#129663`, `#129658`, `#129657`, `#129627`, `#129626`, `#129620`, `#129613`, `#129516`, `#129508`, `#129495`)
  - [`microsoft/onnxruntime`](https://github.com/microsoft/onnxruntime/pull/33517) (`#33517`, plus maintainer-merged fix `#28751`)
  - [`iree-org/iree`](https://github.com/iree-org/iree/pull/25088) (`#25088`)
  - [`google/sentencepiece`](https://github.com/google/sentencepiece/pull/1368) (`#1368`)
  - [`EricLBuehler/mistral.rs`](https://github.com/EricLBuehler/mistral.rs/pull/2495) (`#2495`)
  - [`leejet/stable-diffusion.cpp`](https://github.com/leejet/stable-diffusion.cpp/pull/1750) (`#1750`)
  - [`sonos/tract`](https://github.com/sonos/tract/pull/2425) (`#2425`)
  - [`turboderp-org/exllamav3`](https://github.com/turboderp-org/exllamav3/pull/310) (`#310`)
  - [`mozilla-ai/llamafile`](https://github.com/mozilla-ai/llamafile/pull/1039) (`#1039`)
- **Vector Indexes & Columnar Storage:**
  - [`lance-format/lance`](https://github.com/lance-format/lance/pull/8138) (`#8138`)
  - [`unum-cloud/USearch`](https://github.com/unum-cloud/USearch/pull/776) (`#776`)
- **Computer Vision, Image Codecs, Text Shaping & OCR:**
  - [`opencv/opencv`](https://github.com/opencv/opencv/pulls?q=is%3Apr+author%3Aprofessor-moody+is%3Amerged) (`#30577`, `#30262`, `#30261`) & [`opencv/opencv_extra`](https://github.com/opencv/opencv_extra/pulls?q=is%3Apr+author%3Aprofessor-moody+is%3Amerged) (`#1431`, `#1430`)
  - [`harfbuzz/harfbuzz`](https://github.com/harfbuzz/harfbuzz/pulls?q=is%3Apr+author%3Aprofessor-moody+is%3Amerged) (OpenType text shaping: `#6563`, `#6557`, `#6556`)
  - [`tesseract-ocr/tesseract`](https://github.com/tesseract-ocr/tesseract/pulls?q=is%3Apr+author%3Aprofessor-moody+is%3Amerged) (OCR: `#4671`, `#4670`)
  - [`libjxl/libjxl`](https://github.com/libjxl/libjxl/pull/5075) (JPEG XL codec: `#5075`)

### Selected Public CVEs & Security Advisories
- **[CVE-2025-66455](https://github.com/InternLM/lmdeploy/security/advisories/GHSA-2vh9-42vm-xmv2)** (`InternLM/lmdeploy`) - Untrusted deserialization in model loading (`GHSA-2vh9-42vm-xmv2`).
- **[CVE-2026-14647](https://www.cve.org/CVERecord?id=CVE-2026-14647)** (`onnx/onnx`) - Heap out-of-bounds read in ONNX shape inference ([`#8037`](https://github.com/onnx/onnx/pull/8037)).
- **[CVE-2026-70659](https://github.com/leejet/stable-diffusion.cpp/security/advisories/GHSA-6q7q-2v9c-x8m7)** (`leejet/stable-diffusion.cpp`) - Heap out-of-bounds write in the `imatrix` loader (`GHSA-6q7q-2v9c-x8m7`, fixed in [`#1750`](https://github.com/leejet/stable-diffusion.cpp/pull/1750)).
- **[CVE-2026-78147](https://www.cve.org/CVERecord?id=CVE-2026-78147)**, **[CVE-2026-78148](https://www.cve.org/CVERecord?id=CVE-2026-78148)**, **[CVE-2026-86317](https://www.cve.org/CVERecord?id=CVE-2026-86317)**, **[CVE-2026-17500](https://www.cve.org/CVERecord?id=CVE-2026-17500)**, **[CVE-2026-17501](https://www.cve.org/CVERecord?id=CVE-2026-17501)** & **[CVE-2026-18581](https://www.cve.org/CVERecord?id=CVE-2026-18581)** (`ggml-org/llama.cpp`) - `ggml-rpc` and GGUF parser/loader vulnerabilities.
- **[CVE-2026-10298](https://www.cve.org/CVERecord?id=CVE-2026-10298)**, **[CVE-2026-17512](https://www.cve.org/CVERecord?id=CVE-2026-17512)** & **[CVE-2026-17513](https://www.cve.org/CVERecord?id=CVE-2026-17513)** (`ggml-org/whisper.cpp`) - Heap out-of-bounds read, null dereference, and reachable assertions in model/audio parsing.
- **[CVE-2026-84286 / CERT/CC VU#369611](https://kb.cert.org/vuls/id/369611)** (`turboderp-org/exllamav3`) - Out-of-bounds function-pointer dispatch in reconstruct kernel (`#310`).
- **[CVE-2026-86288](https://www.cve.org/CVERecord?id=CVE-2026-86288)** (`ModelCloud/GPTQModel`) - Device out-of-bounds read from unchecked `g_idx` in Triton dequantization ([`#2950`](https://github.com/ModelCloud/GPTQModel/pull/2950)).
- **[CVE-2026-86289](https://www.cve.org/CVERecord?id=CVE-2026-86289)** (`ollama/ollama`) - Integer-underflow panic in GGUF v1 string parsing ([`#17062`](https://github.com/ollama/ollama/pull/17062)).
- **[CVE-2026-75090](https://www.cve.org/CVERecord?id=CVE-2026-75090)** (`EricLBuehler/mistral.rs`) & **[CVE-2026-75093](https://www.cve.org/CVERecord?id=CVE-2026-75093)** (`sonos/tract`) - GGUF token-ID out-of-bounds panic ([`#2282`](https://github.com/EricLBuehler/mistral.rs/pull/2282)) and NNEF parser crash.
- **[CERT/CC VU#681158](https://m00dy.sh/notes/when-an-hnsw-index-lies-about-its-capacity)** (`nmslib/hnswlib` & `spotify/voyager`) - Heap out-of-bounds write during HNSW index deserialization when header capacity relationships are violated.
