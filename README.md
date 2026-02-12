<div align="center">

# ABot-N0

### A Unified VLA Foundation Model for Versatile Embodied Navigation

[![Paper](https://img.shields.io/badge/📄-Technical_Report-blue)](https://github.com/amap-cvlab/ABot-Navigation/blob/ABot-N0/ABot-N0_Technical_Report.pdf)
[![Project Page](https://img.shields.io/badge/🌐-Project_Page-green)](https://amap-cvlab.github.io/ABot-Navigation/ABot-N0/)

**AMAP CV Lab**

</div>

---

## 🔥 News

- **[2025/07]** 🎉 Technical Report released! [Read the paper](https://github.com/amap-cvlab/ABot-Navigation/blob/ABot-N0/ABot-N0_Technical_Report.pdf)

## 📖 Introduction

**ABot-N0** is a unified **Vision-Language-Action (VLA)** foundation model that achieves a **"Grand Unification"** across **5 core embodied navigation tasks**:

| Task | Description |
|:---:|:---|
| 🎯 **Point-Goal** | Reach precise metric coordinates for robust locomotion and obstacle avoidance |
| 🔍 **Object-Goal** | Search for and navigate to a specific object category in unseen environments |
| 📝 **Instruction-Following** | Execute complex natural language navigation instructions |
| 📍 **POI-Goal** | Navigate to specific Points of Interest and their physical entrances |
| 🚶 **Person-Following** | Real-time tracking and following of dynamic human targets |

ABot-N0 adopts a hierarchical **"Brain-Action"** architecture:
- **Universal Multi-Modal Encoder** — unifies heterogeneous inputs (RGB, visual history, goals) into a shared latent space
- **Cognitive Brain** — a pre-trained LLM (Qwen3-4B) for deep semantic understanding and spatial reasoning
- **Action Expert** — Flow Matching-based trajectory generator for precise, continuous control

## 📊 Key Highlights

| | |
|:---|:---|
| **Unified Tasks** | 5 core navigation paradigms in a single model |
| **SOTA Benchmarks** | New state-of-the-art on **7** authoritative benchmarks |
| **Data Scale** | **16.9M** expert trajectories + **5.0M** reasoning samples |
| **3D Scenes** | **7,802** high-fidelity scenes covering **10.3 km²** |
| **Real-world Deployment** | Deployed on Unitree Go2 with NVIDIA Jetson Orin NX, achieving 2Hz VLA inference |

## 🏗️ Architecture

ABot-N0 follows a hierarchical "Brain-Action" design comprising three pillars:

1. **Universal Multi-Modal Encoder**: Supports flexible vision inputs (panoramic / front-view), heterogeneous goal definitions (text-based semantic goals & point-based geometric goals), and reasoning task encoding.

2. **Cognitive Brain**: Built upon a pre-trained LLM, it supports dual-mode operation — a *Reasoning Head* for high-level semantic understanding and an *Action Head* for motion planning.

3. **Action Expert**: Employs Flow Matching to generate multi-modal trajectory distributions (5 waypoints with position + yaw), enabling precise continuous control.

## 📦 Data Engine

The **ABot-N0 Data Engine** is the largest embodied navigation data pipeline, integrating three synergistic layers:

- **High-Fidelity 3D Scene Ecosystem**: 7,802 scenes (indoor: homes, offices, malls, stations; outdoor: intersections, parks, virtual city) covering 10.3 km²
- **Universal Trajectories Dataset**: ~16.9M expert trajectories across 5 navigation paradigms
- **Cognitive Reasoning Dataset**: ~5.0M reasoning samples grounding decision-making in spatial-social logic

## 🏋️ Training Recipe

ABot-N0 is trained via a three-stage curriculum:

1. **Phase 1 — Cognitive Warm-up**: Fine-tune the LLM backbone on reasoning tasks to learn "what to see" and "how to reason"
2. **Phase 2 — Unified Sensorimotor SFT**: Joint multi-task training with dual-head optimization (AR reasoning + Flow Matching actions)
3. **Phase 3 — SAFE-GRPO**: Post-training value alignment via socially-aware reinforcement learning for social compliance

## 🤖 Agentic Navigation System

Beyond the foundation model, we propose an **Agentic Navigation System** for real-world deployment:

- **Agentic Planner**: VLM-powered intent decomposition with CoT reasoning and closed-loop self-reflection
- **Topo-Memory (Map-as-Memory)**: Hierarchical topological memory for cross-scale spatial knowledge (Block → Road → Function → Object/POI layers)
- **Neural Controller**: High-speed reactive control (>10Hz) bridging strategic waypoints and real-time execution
- **Hardware**: Unitree Go2 quadrupedal robot + NVIDIA Jetson Orin NX (157 TOPS)

## 📈 Benchmark Results

ABot-N0 achieves **new SOTA** on 7 benchmarks:

- **CityWalker** (Point-Goal, Open-Loop)
- **SocNav** (Point-Goal, Closed-Loop)
- **VLN-CE R2R** (Instruction-Following)
- **VLN-CE RxR** (Instruction-Following)
- **HM3D-OVON** (Object-Goal)
- **BridgeNav** (POI-Goal)
- **EVT-Bench** (Person-Following)

## 📅 Release Plan

We are committed to progressively open-sourcing resources to support the research community:

| Phase | Content | Status |
|:---:|:---|:---:|
| Phase 1 | Technical Report | ✅ Released |
| Phase 2 | Data             | 🔜 Coming Soon |
| Phase 3 | Code             | 🔜 Coming Soon |

> **⚠️ Note on Data Release**: Due to privacy and security concerns associated with certain data, we will conduct thorough data cleaning and de-identification before releasing a compliant version for community research use. We prioritize data compliance over release speed — thank you for your patience and understanding.

## 📄 Citation

If you find this work useful, please consider citing:

```bibtex
Coming soon.
```

## 📜 License

This project is released under the [Apache 2.0 License](LICENSE).

## 🙏 Acknowledgments

This work is developed by **AMAP CV Lab**. See the [Technical Report](https://github.com/amap-cvlab/ABot-Navigation/blob/ABot-N0/ABot-N0_Technical_Report.pdf) for a full list of contributors.
