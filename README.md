<h1 align="center">👋 Hi, I'm Zhengpeng Liu</h1>
<p align="center">
  <b>AI for Science · Industrial CAE Software · Composite Mechanics</b><br>
</p>

---

## 🎓 Background

- **M.Eng.** Aerospace Engineering, Xi'an Jiaotong University — GPA 3.89/4.0
- **B.Eng.** Engineering Mechanics, Wuhan University of Science and Technology — GPA 3.77/4.0
- **Intern** Beijing Shenzhou Aerospace Software Technology Co., Ltd. — Industrial CAE R&D

---

## 🔬 Research Interests

> Bridging **computational solid mechanics** and **machine learning** to build next-generation intelligent simulation tools.

- **AI for Science (AI4S):** Physics-informed & data-driven models for materials and structures
- **Composite Materials Mechanics:** Failure criteria, constitutive modeling, damage evolution, multi-scale analysis
- **Intelligent CAE:** ML-accelerated solvers, surrogate modeling, reduced-order models (ROM)
- **Industrial Software R&D:** CAD/CAE kernel development, solver architecture, FreeCAD secondary development

---

## 🛠️ Technical Skills

### Simulation & FEA
- **ABAQUS Secondary Development:** Parametric modeling (Python scripting / GUI plugins), UMAT/VUMAT/USDFLD subroutine authoring, cohesive element and PBC applying
- Structural analysis: buckling, progressive damage, thermo-mechanical coupling

### Machine Learning / Deep Learning
- **Architectures:** DNN · CNN (ResNet) · ICNN (Input Convex NN) · GAN · DeepONet · PINNs
- **Applications:** Failure envelope prediction, surrogate constitutive modeling, operator learning for PDEs, deep transfer learning (DTL)
- Frameworks: PyTorch · TensorFlow · Scikit-learn
- LLM/Agent: Ollama · ChromaDB · LangChain · Claude Code (agentic workflows)

### Programming & HPC
- **Python** — ML pipelines, ABAQUS scripting, GUI (PyQt6 / PyVista), scientific computing
- **C++ / Fortran** — Solver kernels, constitutive model implementation (Eigen, pybind11)
- **Parallel Computing:** OpenMP · MPI · CUDA (cuSPARSE)
- Dev environment: VS2022 · WSL2 (Ubuntu) · Intel oneAPI · Anaconda

---

## 🚀 Selected Projects

| Project | Description | Stack |
|---|---|---|
| **CSDM** | Multi-agent AI system for composite stiffened panel structural design; 6-agent pipeline from NL input → LLM candidate gen + RAG retrieval + surrogate screening → ABAQUS FEM validation → report | Python · LLM · RAG · ABAQUS |
| **MDD-TFC** | Model-data-driven transverse failure criterion for UD-CFRP; ResNet-101 + Tsai-Wu + ICNN maps RVE microstructure to full failure envelope via only 4 load cases; validated via few-shot transfer learning (*TWS* Q1, 1st author) | PyTorch · ABAQUS |
| **FE-NN-KT** | Multi-scale homogenization framework: offline RVE sampling → surrogate constitutive model training → online FE-NN macro solver; coarse-to-fine transfer reduces data cost 3.3×, macro analysis 20× faster than DNS | PyTorch · ABAQUS · Q4 FEM |
| **Composite Intelligent Design Platform** | Hierarchical design platform (microstructure → laminate → stiffened panel → fuselage); sub-second inference with per-level AI models; supports user fine-tuning | PyQt6 · TF · PyTorch |
| **CAE FEM Software** | Lightweight FEM solver: PyQt6 + PyVista frontend, C++/Eigen compute core, pybind11 bridge, Gmsh meshing, real-time stress/displacement rendering | C++ · PyQt6 · pybind11 · Gmsh |

---

## 📄 Publications, Copyrights & Awards

**Papers (2 SCI papers, total IF 15.5):**
- 📝 **Liu Z**, et al. A model and data-driven transverse failure criterion for UD-CFRP composites. *Thin-Walled Structures*, 2026. (**Q1 Top, 1st author**)
- 📝 Wang Q, Li Z, **Liu Z**, et al. Interpretable prediction of ultimate strength of composite pressure hulls using symbolic regression. *Composites Part A*, 2026. (Q2 Top, 3rd author)

**Software Copyrights (4×, all 1st inventor):**
- 💻 航空复合材料多层级智能设计平台 V1.0
- 💻 复合材料参数化建模ABAQUS插件 V1.0
- 💻 通用CAE求解系统 V1.0
- 💻 Neper-PFC数据转化接口 V1.0

**Awards:**
- 🏆 Competition: MCM/ICM M Prize · 华为杯研究生数学建模二等奖 · 全国大学生数学竞赛二等奖 · 20+ total
- 🎓 Scholarships: National Scholarship (2023)

---

## 💼 What I Can Help With

- Custom ABAQUS plugins & batch simulation pipelines (parametric modeling, pre/post-processing)
- UMAT/VUMAT subroutine development for composite constitutive models
- ML surrogate models for mechanical property prediction & inverse design
- Multi-agent AI systems for simulation automation (LLM + RAG + FEM in the loop)
- DeepONet / PINN implementation for engineering PDE problems
- CAE solver prototyping with C++/Python/Fortran hybrid architecture

---

## 📬 Contact

- 📧 [lzp03@stu.xjtu.edu.cn](mailto:lzp03@stu.xjtu.edu.cn)
- 💬 WeChat: `lzp13971812916`
- 🐙 GitHub: [@ZPL-03](https://github.com/ZPL-03)
