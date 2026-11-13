<h1 align="center">Zhengpeng Liu | 刘正鹏</h1>

<p align="center">
  <a href="https://github.com/ZPL-03">简体中文</a> | <strong>English</strong>
</p>

<p align="center">
  <strong>AI for Solid Mechanics · Industrial CAE Software · Engineering Agents</strong>
</p>

<p align="center">
  M.Eng. candidate at Xi'an Jiaotong University, working on AI for Science (AI4S) and AI for Engineering (AI4E).
</p>

## About

- M.Eng. candidate at Xi'an Jiaotong University through graduate recommendation, GPA 3.89/4.0.
- B.Eng. in Engineering Mechanics from Wuhan University of Science and Technology, GPA 3.77/4.0.
- Research interests: AI for Science (AI4S) and AI for Engineering (AI4E).
- Working at the intersection of AI and solid mechanics, with a focus on AI-accelerated simulation, intelligent modeling, and industrial CAE software.

## Focus

- **AI-assisted modeling:** CAD modeling-context understanding, workflow assistance, and human-in-the-loop interaction.
- **AI-accelerated simulation:** surrogate models, reduced-order models, physics-constrained learning, and digital twins.
- **Industrial CAD/CAE software:** geometry and meshing algorithms, solver integration, and simulation workflow tooling.
- **Engineering agents:** natural-language requirement parsing, structured contracts, tool orchestration, knowledge feedback, and traceable analysis reports.

## Featured Open-source Projects

### [MechAgent](https://github.com/ZPL-03/MechAgent)

An open-source multi-agent orchestration framework for natural-language CAE/FEA workflows. It organizes and audits simulation processes through Pydantic v2 contracts connecting Planner, Designer, MeshAgent, SolverAgent, PostProcAgent, AnalystAgent, and ReporterAgent. It includes Gmsh and CalculiX adapters and provides a local Studio, CLI, and Python SDK.

`Python` `LangGraph` `Pydantic v2` `Gmsh` `CalculiX` `3D Visualization`

### [CSDM_panel](https://github.com/ZPL-03/CSDM_panel)

A six-agent design system for composite stiffened panels. Its workflow covers natural-language task parsing, candidate generation through LLMs, case transfer, and DOE, RF/MLP surrogate screening, Abaqus verification, knowledge feedback, and Markdown/PDF reports.

`Python` `PyQt6` `Abaqus` `Surrogate Model` `RAG` `Knowledge Graph` `ChromaDB`

### [CSAgent](https://github.com/ZPL-03/CSAgent)

An intelligent design platform for composite cylindrical pressure hulls under external pressure. A LangGraph state graph coordinates six agents. ASME RD-1172 and PBIPF provide initial screening, while Abaqus linear buckling and Static Riks analyses verify ultimate pressure. SQLite stores events, tool calls, and state snapshots, and a PyQt6 workbench presents candidates, FEA results, and audit reports.

`Python` `LangGraph` `SQLite` `PyQt6` `Abaqus Buckling/Riks` `RAG/KG`

### [CSGPT](https://github.com/ZPL-03/CSGPT)

A domain LLM and full-stack expert system for composite-structure design. The data pipeline covers document parsing/OCR, RAG chunking, knowledge graph extraction, and SFT. The model service uses Qwen3-14B LoRA and an OpenAI-compatible vLLM endpoint. The web application supports streaming chat, web retrieval, and knowledge graph exploration with Cytoscape.js.

`Next.js 14` `React` `TypeScript` `Prisma` `PostgreSQL` `LLaMA-Factory` `vLLM`

### [A General Solution Platform for CAE](https://github.com/ZPL-03/A-General-Solution-Platform-for-CAE)

An open-source CAE prototype. PyQt6 provides the pre- and post-processing interface, Gmsh handles parametric geometry and meshing, VTK/PyVista renders results, C++17/Eigen implements the solver core, and pybind11 exposes Python bindings. The current project covers tetrahedral/hexahedral meshes and linear, nonlinear, and modal analysis workflows.

`C++17` `Eigen` `pybind11` `PyQt6` `Gmsh` `VTK/PyVista` `CMake`

### [Multi-level Intelligent Design Platform for Aviation Composites](https://github.com/ZPL-03/AC-GPT)

A desktop platform integrating parametric modeling, performance surrogates, and lightweight optimization across microstructure, laminate, and stiffened-structure levels. It also provides material management, model loading, and fine-tuning with user data.

`Python` `PyQt6` `TensorFlow` `PyTorch` `NumPy/SciPy` `Visualization`

### Abaqus RVE Toolchain

[2D RVE](https://github.com/ZPL-03/2D_RVE_Script) · [3D RVE](https://github.com/ZPL-03/3D_RVE_Script) · [3D RVE with Voids](https://github.com/ZPL-03/3D_RVE_Script_With_Viods) · [Short-fiber RVE](https://github.com/ZPL-03/3D_RVE_Script_SFRC_MP-PBC)

Parametric Abaqus scripts for unidirectional continuous-fiber, porous, and random short-fiber microstructures. The toolchain covers random fiber generation, periodic mirroring, interference checks, material and interface definitions, meshing, periodic boundary conditions, and geometry export.

## AI-Accelerated Simulation

### FE-NN-KT Multiscale Constitutive Surrogate

```text
Abaqus RVE parametrization and PBCs
  -> Offline batch sampling
  -> Pre-training on coarse-mesh source-domain data
  -> Transfer fine-tuning on fine-mesh target-domain data
  -> Neural prediction of first Piola stress P
  -> Consistent tangent A through automatic differentiation
  -> Q4 plane-strain FEM and Newton-Raphson iterations
  -> Comparison with Abaqus DNS
```

The surrogate replaces direct RVE solves at integration points while the macroscopic equilibrium equations remain governed by the finite element solver. Compared with full fine-mesh sampling, the workflow reduces offline high-fidelity data cost by approximately 3.3 times and provides an approximately 20-times speedup over DNS in online macroscopic analysis.

### Microstructure-sensitive Transverse Failure Criterion

ResNet-101 encodes random fiber microstructures, material-system and microstructure corrections augment the Tsai-Wu criterion, and an ICNN constrains the geometry of the failure envelope. The method reconstructs the transverse failure envelope from four basic loading cases and forms the basis of a paper published in *Thin-Walled Structures*.

### Physics-constrained Progressive Damage Response Prediction

A CNN encodes microstructures, an MLP encodes material parameters, and an LSTM represents loading history. The training objective combines data error with constraints on initial stiffness, post-peak stiffness degradation, and energy dissipation to predict stress-strain curves under uniaxial and biaxial loading.

### Graph-based Full-field Surrogate Prototype

The prototype maps an FEM mesh to a graph of nodes and edges, uses a Graph Transformer to aggregate multi-hop structural information, and decodes nodal field variables. The currently verifiable scope is a Phase A prototype for buckling-mode displacement fields of composite stiffened panels.

## Experience

| Period | Organization / Project | Focus |
| --- | --- | --- |
| 2026.07-2026.09 | Huawei Technologies, Algorithm Intern | AI-assisted modeling: developed an in-process Creo DLL with Pro/TOOLKIT C++ for model parsing and Top-3 interaction; implemented inference and caching in a Python worker |
| 2025.09-2026.06 | Beijing Shenzhou Aerospace Software Technology Co., Ltd., R&D Intern | Open-source CAE architecture, multi-level intelligent composite design, integration-point constitutive surrogates, and mesh-level field surrogate exploration |
| 2025.09-2026.06 | Industry-sponsored research project | Domain LLM, expert question-answering system, and multi-agent intelligent design system for composite structures |
| 2023.11-2026.05 | Research project | High-fidelity parametric modeling and simulation of RVEs, laminates, and stiffened panels; user subroutines; forward performance prediction and inverse lightweight design |

## Publications & Outputs

### Publications

1. **Liu Z**, Wang Q, Li Z, et al. [A model and data-driven transverse failure criterion for UD-CFRP composites by considering microstructure distribution and material variation](https://doi.org/10.1016/j.tws.2026.114751). *Thin-Walled Structures*, 2026, 114751. First author.
2. Wang Q, Li Z, **Liu Z**, et al. [Interpretable prediction of ultimate strength of composite pressure hulls using data-driven symbolic regression](https://doi.org/10.1016/j.compositesa.2026.109863). *Composites Part A: Applied Science and Manufacturing*, 2026, 207: 109863. Third author.

### Intellectual Property

- Multi-agent and domain-LLM-enhanced intelligent design system for composite pressure hulls. Patent application, first inventor.
- Multi-level Intelligent Design Platform for Aviation Composites V1.0 (2026R11L0903472, primary contributor).
- Abaqus Parametric Modeling Plugin for Composite Materials V1.0 (2026SR0649202, primary contributor).
- General CAE Solution System V1.0 (2026SR0649266, primary contributor).
- Neper-PFC Data Conversion Interface V1.0 (2023SR1283601, primary contributor).

## Tech Stack

| Area | Technologies |
| --- | --- |
| Mechanical simulation / modeling | Abaqus, ANSYS, Creo, SolidWorks |
| ML / DL | PyTorch, TensorFlow, Scikit-learn, DNN, CNN, GNN, RNN, ICNN, DeepONet, PINN, transfer learning |
| LLM / Agent | PEFT, LLaMA-Factory, vLLM, Ollama, LangChain, LangGraph, RAG, ChromaDB, Neo4j |
| CAE development | Python, C++17, Fortran, CMake, Eigen, pybind11, MKL, OpenMP, MPI, CUDA/cuSPARSE, Gmsh, VTK, OpenCASCADE |
| Full-stack development | Next.js 14, React, TypeScript, Zustand, Prisma, PostgreSQL, Cytoscape.js, Vercel, Cloudflare |

## Selected Awards

- National Scholarship and Outstanding Graduate Student recognition.
- 2023 MCM/ICM Meritorious Winner, top 6%.
- Second Prize in the Huawei Cup Graduate Mathematical Contest in Modeling, top 13%.
- Second Prize in the Chinese Mathematics Competitions for College Students.
- More than 20 awards in mechanics, mathematics, mathematical modeling, and industrial AI competitions.

## Collaboration Interests

- Abaqus parametric modeling scripts and user subroutines.
- Surrogate models for forward prediction and inverse design of materials and structures.
- LLM post-training, RAG, knowledge graphs, and engineering agent applications.
- Industrial AI algorithm development.

## Contact

- GitHub: [@ZPL-03](https://github.com/ZPL-03)
- Online project: [CSGPT](https://csgpt.ipen03.com)
- Email: [lzp03@stu.xjtu.edu.cn](mailto:lzp03@stu.xjtu.edu.cn)
