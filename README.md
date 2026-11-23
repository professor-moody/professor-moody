# Nathan (`m00dy` / `@professor-moody`)

I am Nathan (`m00dy`), a security researcher and penetration tester focused on **AI/ML runtime security**, **binary format and parser verification**, **weight-space analysis**, and **adversarial tradecraft simulation**.

My work centers on finding memory-safety, type-confusion, integer-overflow, and deserialization defects across the native C, C++, and Rust software stack that loads and executes machine learning models and binary containers, alongside building open-source tooling for red-team infrastructure, post-exploitation research, and defensive telemetry validation.

- **Notebook & Writing:** [m00dy.sh](https://m00dy.sh)
- **Public Advisories & Patch Map:** [m00dy.sh/advisories](https://m00dy.sh/advisories)
- **The Unchecked Atlas:** [unchecked.sh](https://unchecked.sh)
- **GitHub:** [github.com/professor-moody](https://github.com/professor-moody)

---

## Research & Open-Source Projects

### AI/ML Security & Parser Verification
- **[Secant](https://github.com/professor-moody/secant)** ([Docs](https://professor-moody.github.io/secant/)) - Rust and Python toolkit for **Weight-Space Programming (WSP)** covering zero-evaluation spectral weight auditing (`secant inspect` / `read`), multi-subspace Gram-Schmidt composition with closed-form Target-Shift Calibration (`secant compose`), zero-copy `mmap` plus `Q8_0` and `Q4_K` block-aligned quantized surgery (`secant patch` / `quant patch`), preload spectral sanitization, and subspace-locked LoRA micro-training (`ProjectThenHealLinear`).
- **[Crucible](https://github.com/professor-moody/crucible)** ([Docs](https://professor-moody.github.io/crucible/)) - Structure-aware grammar, static contract synthesis, and mutation framework for ML model and binary container formats (`GGUF`, `ONNX`, `SafeTensors`, `TFLite`, `Core ML milblob/mlpackage`, `Protobuf/upb`, `FlatBuffers/FlexBuffers`, `ISOBMFF`, `PNG`, `RESP`) pairing field-coupled Rust FFI mutators with sanitizer-instrumented harnesses, differential oracles, and stack-hash crash deduplication.
- **[The Unchecked Atlas](https://unchecked.sh)** - Interactive vulnerability research atlas mapping parser boundaries, container deserialization hazards, and native runtime memory-safety invariants across modern systems and ML stacks.

### Adversarial Tradecraft, Emulation & Infrastructure
- **[scorch](https://github.com/professor-moody/scorch)** (`47★`) & **[ludus_scorch](https://github.com/professor-moody/ludus_scorch)** (`19★`) - Cross-platform offensive security toolkit for Microsoft System Center Orchestrator (SCORCH) covering security assessment, API enumeration, credential extraction, and runbook execution, paired with its [Ludus](https://ludus.cloud) Ansible collection for automated lab deployment.
- **[ludus_litterbox_role](https://github.com/professor-moody/ludus_litterbox_role)** (`21★`) - Ludus Ansible role for deploying the LitterBox static/dynamic malware analysis and payload testing sandbox on Windows lab VMs.
- **[halo-forge](https://github.com/professor-moody/halo-forge)** (`10★`) - Cross-vendor local finetuning workstation supporting SFT, CPT, DPO, GRPO, and RAFT with verifier-grounded rewards and runtime-qualified accelerator paths.
- **[aipostex](https://github.com/professor-moody/aipostex)** (`6★`), **[aipostex-templates](https://github.com/professor-moody/aipostex-templates)** & **[aipostex-lab](https://github.com/professor-moody/aipostex-lab)** - Single-binary Go AI infrastructure offensive security framework (`131` templates, `20` exploit modules) targeting LLM gateways, model registries, inference servers, vector databases, Jupyter notebooks, and MCP tool servers, alongside its reproducible test lab.
- **[hemlock](https://github.com/professor-moody/hemlock)** - Portable Go RAG pipeline poisoning document generator for authorized security assessments (operationalizing PoisonedRAG and PhantomText across 11 document formats, 63 hiding techniques, 75 payload templates, and 4 framework validators for LangChain, LlamaIndex, Unstructured.io, and Haystack).

---

## Accepted Upstream Contributions & Published Advisories

### Merged Upstream Patches (57 Authored Merged PRs + 14 Maintainer-Merged Fixes Across 26 Repositories)
- **ML Runtimes, Compilers, Serialization & Tokenizers:**
  - [`tensorflow/tensorflow`](https://github.com/tensorflow/tensorflow/pulls?q=is%3Apr+author%3Aprofessor-moody+is%3Amerged) (19 merged PRs across `core/framework`, `core/kernels`, `core/grappler`, `core/saved_model`, `core/util/tensor_bundle`, and `core/lib/jpeg`/`webp`: `#130078`, `#129866`, `#129806`, `#129804`, `#129690`, `#129689`, `#129688`, `#129671`, `#129663`, `#129658`, `#129657`, `#129654`, `#129627`, `#129626`, `#129620`, `#129613`, `#129516`, `#129508`, `#129495`)
  - [`protocolbuffers/protobuf`](https://github.com/protocolbuffers/protobuf/commits/main?author=professor-moody) (9 merged `upb` C runtime PRs via Copybara across arena sizing, MiniTable layout counters, extension arrays, and ProtoJSON codecs: `#31236`, `#31128`, `#31104`, `#31097`, `#31010`, `#30959`, `#30958`, `#30787`, `#30785`)
  - [`openxla/xla`](https://github.com/openxla/xla/commits/main?author=professor-moody) (5 merged PRs via Copybara across `xla/service` and `xla/tsl/lib/io`: `#52787`, `#52698`, `#52513`, `#52416`, `#51992`)
  - [`microsoft/onnxruntime`](https://github.com/microsoft/onnxruntime/pull/33517) (`#33517`, plus maintainer-merged fix `#28751`)
  - [`onnx/onnx`](https://github.com/onnx/onnx/pull/8037) (maintainer-merged fix `#8037` for `CVE-2026-14647`)
  - [`iree-org/iree`](https://github.com/iree-org/iree/pull/25088) (`#25088`)
  - [`google/sentencepiece`](https://github.com/google/sentencepiece/pull/1368) (`#1368`)
  - [`EricLBuehler/mistral.rs`](https://github.com/EricLBuehler/mistral.rs/pulls?q=is%3Apr+author%3Aprofessor-moody+is%3Amerged) (`#2495`, plus maintainer-merged fix `#2282` for `CVE-2026-75090`)
  - [`leejet/stable-diffusion.cpp`](https://github.com/leejet/stable-diffusion.cpp/pull/1750) (`#1750`, plus maintainer-merged fixes `#1832` for `CVE-2026-115571` and `#1404` for `GHSA-fc82-rcm2-p4vr`)
  - [`sonos/tract`](https://github.com/sonos/tract/pull/2425) (`#2425`, plus maintainer-merged fixes `#2413` for `CVE-2026-75093` and `#2411` for `CVE-2026-133616`)
  - [`turboderp-org/exllamav3`](https://github.com/turboderp-org/exllamav3/pull/310) (`#310`)
  - [`mozilla-ai/llamafile`](https://github.com/mozilla-ai/llamafile/pull/1039) (`#1039`, plus maintainer-merged fix `#1044` for `CVE-2026-133498`)
  - [`ollama/ollama`](https://github.com/ollama/ollama/pull/17062) (maintainer-merged fix `#17062` for `CVE-2026-86289`)
  - [`ModelCloud/GPTQModel`](https://github.com/ModelCloud/GPTQModel/pull/2950) (maintainer-merged fix `#2950` for `CVE-2026-86288`)
  - [`ml-explore/mlx`](https://github.com/ml-explore/mlx/pull/4179) (maintainer-merged GGUF bounds fix `#4179`)
- **Vector Indexes & Columnar Storage:**
  - [`facebookresearch/faiss`](https://github.com/facebookresearch/faiss/pull/5764) (`#5764`)
  - [`lance-format/lance`](https://github.com/lance-format/lance/pull/8138) (`#8138`)
  - [`unum-cloud/USearch`](https://github.com/unum-cloud/USearch/pull/776) (`#776`)
  - [`spotify/voyager`](https://github.com/spotify/voyager/commit/2e68582c8bd6e22cd14fd3a25f11b720b0fa166b) (maintainer-merged fix `2e68582` for `CVE-2026-124959`)
- **Computer Vision, Image/3D Codecs, Text Shaping & OCR:**
  - [`opencv/opencv`](https://github.com/opencv/opencv/pulls?q=is%3Apr+author%3Aprofessor-moody+is%3Amerged) (`#30577`, `#30262`, `#30261`) & [`opencv/opencv_extra`](https://github.com/opencv/opencv_extra/pulls?q=is%3Apr+author%3Aprofessor-moody+is%3Amerged) (`#1431`, `#1430`)
  - [`harfbuzz/harfbuzz`](https://github.com/harfbuzz/harfbuzz/pulls?q=is%3Apr+author%3Aprofessor-moody+is%3Amerged) (OpenType text shaping: `#6563`, `#6557`, `#6556`, plus maintainer-merged fixes `#6546` and `#6542`)
  - [`tesseract-ocr/tesseract`](https://github.com/tesseract-ocr/tesseract/pulls?q=is%3Apr+author%3Aprofessor-moody+is%3Amerged) (OCR: `#4671`, `#4670`)
  - [`pnggroup/libpng`](https://github.com/pnggroup/libpng/pull/973) (APNG sequential reader: `#973`)
  - [`python-pillow/Pillow`](https://github.com/python-pillow/Pillow/pull/10500) (`#10500`)
  - [`google/filament`](https://github.com/google/filament/pull/10644) (`#10644`)
  - [`libjxl/libjxl`](https://github.com/libjxl/libjxl/pull/5075) (JPEG XL codec: `#5075`)

### Public CVEs & CERT/CC Vulnerability Notes (26 Public CVEs + 3 CERT/CC `VU#` Advisories)
- **[CVE-2026-124959 / CERT/CC VU#681158](https://www.cve.org/CVERecord?id=CVE-2026-124959)** (`nmslib/hnswlib` & `spotify/voyager`) - Heap out-of-bounds write during HNSW index deserialization when header capacity invariants are violated ([write-up](https://m00dy.sh/notes/when-an-hnsw-index-lies-about-its-capacity)).
- **[CERT/CC VU#162455](https://m00dy.sh/notes/when-a-shared-rpc-server-hands-back-uncleared-heap)** (`ggml-org/llama.cpp`) - Cross-client uninitialized heap memory disclosure via `GET_TENSOR` in `ggml-rpc` (`#20832`).
- **[CVE-2026-133498](https://www.cve.org/CVERecord?id=CVE-2026-133498)** (`mozilla-ai/llamafile`) - Declared zip entry size wraparound and out-of-bounds read in `llamafile_open_zip` ([`#1038`](https://github.com/mozilla-ai/llamafile/issues/1038), [`#1039`](https://github.com/mozilla-ai/llamafile/pull/1039), [`#1044`](https://github.com/mozilla-ai/llamafile/pull/1044)).
- **[CVE-2026-133621](https://www.cve.org/CVERecord?id=CVE-2026-133621)** (`shader-slang/slangpy`) - Heap out-of-bounds read in vendored `tinyexr::DecodePixelData` on truncated OpenEXR scanlines ([`#1239`](https://github.com/shader-slang/slangpy/pull/1239)).
- **[CVE-2026-133610](https://www.cve.org/CVERecord?id=CVE-2026-133610)** (`antirez/gguf-tools`) - Unchecked tensor data offset out-of-bounds read in `gguf_get_tensor` ([`#33`](https://github.com/antirez/gguf-tools/pull/33)).
- **[CVE-2026-133612](https://www.cve.org/CVERecord?id=CVE-2026-133612)** (`SqueezeAILab/SqueezeLLM`) & **[CVE-2026-133499](https://www.cve.org/CVERecord?id=CVE-2026-133499)** (`Vahe1994/AQLM`) - Unchecked quantized index GPU out-of-bounds write in CUDA matvec ([`#77`](https://github.com/SqueezeAILab/SqueezeLLM/issues/77)) and GPU out-of-bounds read in Triton dequantization ([`#191`](https://github.com/Vahe1994/AQLM/issues/191)).
- **[CVE-2026-115571](https://github.com/leejet/stable-diffusion.cpp/security/advisories/GHSA-cfhc-rw9j-rp26)** & **[CVE-2026-70659](https://github.com/leejet/stable-diffusion.cpp/security/advisories/GHSA-6q7q-2v9c-x8m7)** (`leejet/stable-diffusion.cpp`) - Signed-to-unsigned tensor offset wrap (`GHSA-cfhc-rw9j-rp26`, [`#1832`](https://github.com/leejet/stable-diffusion.cpp/pull/1832)) and `imatrix` loader heap out-of-bounds write (`GHSA-6q7q-2v9c-x8m7`, [`#1750`](https://github.com/leejet/stable-diffusion.cpp/pull/1750)).
- **[CVE-2026-84286 / CERT/CC VU#369611](https://kb.cert.org/vuls/id/369611)** (`turboderp-org/exllamav3`) & **[CVE-2026-116502](https://github.com/turboderp-org/exllamav2/issues/817)** (`turboderp-org/exllamav2`) - Out-of-bounds CUDA function-pointer dispatch ([`#310`](https://github.com/turboderp-org/exllamav3/pull/310)) and quantized `g_idx` heap out-of-bounds write.
- **[CVE-2025-66455](https://github.com/InternLM/lmdeploy/security/advisories/GHSA-2vh9-42vm-xmv2)** (`InternLM/lmdeploy`) - Pre-auth untrusted pickle deserialization in Distributed Serving (`GHSA-2vh9-42vm-xmv2`).
- **[CVE-2026-14647](https://www.cve.org/CVERecord?id=CVE-2026-14647)** (`onnx/onnx`) - Heap out-of-bounds read in ONNX convolution shape inference ([`#8037`](https://github.com/onnx/onnx/pull/8037)).
- **[CVE-2026-86288](https://www.cve.org/CVERecord?id=CVE-2026-86288)** (`ModelCloud/GPTQModel`) - GPU out-of-bounds read from unchecked `g_idx` in Triton dequantization ([`#2950`](https://github.com/ModelCloud/GPTQModel/pull/2950)).
- **[CVE-2026-86289](https://www.cve.org/CVERecord?id=CVE-2026-86289)** (`ollama/ollama`) - Integer-underflow panic in GGUF v1 string parsing ([`#17062`](https://github.com/ollama/ollama/pull/17062)).
- **[CVE-2026-75090](https://www.cve.org/CVERecord?id=CVE-2026-75090)** (`EricLBuehler/mistral.rs`) & **[CVE-2026-75093](https://www.cve.org/CVERecord?id=CVE-2026-75093)** / **[CVE-2026-133616](https://www.cve.org/CVERecord?id=CVE-2026-133616)** (`sonos/tract`) - GGUF token-ID vocabulary out-of-bounds panic ([`#2282`](https://github.com/EricLBuehler/mistral.rs/pull/2282)), raw tensor extent mismatch panic ([`#2413`](https://github.com/sonos/tract/pull/2413)), and `Gemm` operand arity out-of-bounds panic ([`#2411`](https://github.com/sonos/tract/pull/2411)).
- **[CVE-2026-78147](https://www.cve.org/CVERecord?id=CVE-2026-78147)**, **[CVE-2026-78148](https://www.cve.org/CVERecord?id=CVE-2026-78148)**, **[CVE-2026-86317](https://www.cve.org/CVERecord?id=CVE-2026-86317)**, **[CVE-2026-17500](https://www.cve.org/CVERecord?id=CVE-2026-17500)**, **[CVE-2026-17501](https://www.cve.org/CVERecord?id=CVE-2026-17501)** & **[CVE-2026-18581](https://www.cve.org/CVERecord?id=CVE-2026-18581)** (`ggml-org/llama.cpp`) - `ggml-rpc`, JSON-schema grammar, and template parser vulnerabilities.
- **[CVE-2026-10298](https://www.cve.org/CVERecord?id=CVE-2026-10298)**, **[CVE-2026-17512](https://www.cve.org/CVERecord?id=CVE-2026-17512)** & **[CVE-2026-17513](https://www.cve.org/CVERecord?id=CVE-2026-17513)** (`ggml-org/whisper.cpp`) - Heap out-of-bounds read, null dereference, and reachable assertions in model/audio parsing.
