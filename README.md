Aegis-AI: Autonomous Edge Threat Detection & Telemetry Engine
Aegis-AI is a hardware-accelerated, zero-cloud threat detection and spatial telemetry platform purpose-built for Snapdragon-powered HP PCs. Leveraging the Qualcomm® AI Engine Direct SDK (QNN) and Qualcomm AI Hub, it offloads multi-stream vision models directly to the 45 TOPS Hexagon™ NPU—delivering microsecond-level edge inference with absolute data privacy and zero network egress.

⚡ Key Highlights
Zero Egress Privacy: Sensitive visual and system-event telemetry data never leaves host memory, ensuring complete data sovereignty.

NPU Hardware Offloading: Sustained real-time inference (YOLOv8s INT8) executes directly on the Qualcomm Hexagon NPU, freeing up the Oryon™ CPU and Adreno™ GPU for parallel workflows.

Security Hardware Integration: Easily ingests RTSP video feeds from local local network security hardware, including CP Plus systems and standard IP cameras, for localized threat processing.

Qualcomm AI Hub Optimization: Models are compiled to native .dlc and QNN graph binaries leveraging INT8 precision for optimal TOPS/Watt performance.

🧠 System Architecture
Plaintext
[ CP Plus / Standard IP Camera RTSP Stream ]
                  │
                  ▼
┌────────────────────────────────────────────────────────┐
│              Host Application (Python / C++)           │
│   Preprocessing (FP32 -> INT8/FP16 Normalization)      │
└─────────────────────────┬──────────────────────────────┘
                          │
                          ▼
┌────────────────────────────────────────────────────────┐
│           Qualcomm AI Engine Direct (QNN / SNPE)       │
├────────────────────────────────────────────────────────┤
│      Execution Delegate: QnnHtp.dll / HTP Backend      │
│  ├── Vision Pipeline: Quantized YOLOv8 Detection       │
│  └── Telemetry Engine: Int8 Threat Classification      │
└─────────────────────────┬──────────────────────────────┘
                          │
                          ▼
┌────────────────────────────────────────────────────────┐
│           Qualcomm Hexagon™ NPU Hardware               │
│       45 TOPS Dedicated Edge Inference Compute         │
└────────────────────────────────────────────────────────┘
🛠️ Tech Stack & SDKs
Platform: HP OmniBook / EliteBook Snapdragon-powered Copilot+ PCs (Windows on ARM64)

AI Acceleration: Qualcomm® AI Engine Direct SDK (QNN v2.20+)

Model Hub: Qualcomm AI Hub (qai-hub)

Application Engine: Python 3.10+ (WoA) / ONNX Runtime QNN Execution Provider (QNNExecutionProvider)

Dashboard: FastAPI + Streamlit for edge telemetry visualization

🚀 Setup & Installation
Prerequisites
Windows 11 on Snapdragon (ARM64).

Qualcomm AI Engine Direct SDK (QNN SDK) configured in system paths.

Python 3.10+ (ARM64 native build).

Installation Steps
Bash
