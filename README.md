<h1 align="center">刘正鹏 | Zhengpeng Liu</h1>

<p align="center">
  <strong>简体中文</strong> | <a href="https://github.com/ZPL-03/ZPL-03/blob/main/README_EN.md">English</a>
</p>

<p align="center">
  <strong>AI for Solid Mechanics · Industrial CAE Software · Engineering Agents</strong>
</p>

<p align="center">
  西安交通大学机械硕士研究生，研究方向：AI for Science (AI4S) / AI for Engineering (AI4E)。
</p>

## 关于我 / About

- 西安交通大学机械硕士研究生 (推免)，GPA 3.89/4.0。
- 武汉科技大学工程力学学士，GPA 3.77/4.0。
- 研究方向：AI for Science (AI4S) / AI for Engineering (AI4E)。
- 围绕 AI 与固体力学交叉，开展 AI 加速仿真、智能建模和工业 CAE 软件研发。

## 当前关注 / Focus

- **AI 辅助建模**：CAD 建模上下文理解、建模流程辅助与人机协同交互。
- **AI 加速仿真**：代理模型、降阶模型、物理约束学习与数字孪生。
- **工业 CAD/CAE 软件**：几何与网格算法、求解器集成和仿真工作流工具链。
- **工程智能体**：自然语言需求解析、结构化契约、工具编排、知识回流与可追溯分析报告生成。

## 精选开源项目 / Featured Open-source Projects

### [MechAgent](https://github.com/ZPL-03/MechAgent)

自然语言驱动的开源 CAE/FEA 多智能体编排框架，项目负责组织和审计仿真流程。系统通过 Pydantic v2 契约连接 Planner、Designer、MeshAgent、SolverAgent、PostProcAgent、AnalystAgent 和 ReporterAgent，内置 Gmsh 网格与 CalculiX 求解适配，提供 Studio、CLI 和 Python SDK。

`Python` `LangGraph` `Pydantic v2` `Gmsh` `CalculiX` `3D Visualization`

### [CSDM_panel](https://github.com/ZPL-03/CSDM_panel)

面向复合材料加筋壁板的六智能体设计系统，完成自然语言任务解析、LLM/案例/DOE 候选生成、RF/MLP 代理预筛、Abaqus 校核、知识回流和 Markdown/PDF 报告。

`Python` `PyQt6` `Abaqus` `Surrogate Model` `RAG` `Knowledge Graph` `ChromaDB`

### [CSAgent](https://github.com/ZPL-03/CSAgent)

复合材料外压圆柱耐压壳智能设计平台。LangGraph 状态图组织六个智能体，ASME RD-1172 与 PBIPF 用于候选初筛，Abaqus 线性屈曲和 Static Riks 用于极限压力校核；SQLite 记录事件、工具调用和状态快照，PyQt6 工作台展示候选、FEM 结果和审计报告。

`Python` `LangGraph` `SQLite` `PyQt6` `Abaqus Buckling/Riks` `RAG/KG`

### [CSGPT](https://github.com/ZPL-03/CSGPT)

面向复合材料结构设计的领域 LLM 与全栈专家系统。数据链路覆盖文档解析/OCR、RAG 切块、知识图谱抽取和 SFT；模型侧使用 Qwen3-14B LoRA 与 vLLM OpenAI-compatible 服务；Web 端支持流式对话、联网检索和 Cytoscape.js 知识图谱浏览。

`Next.js 14` `React` `TypeScript` `Prisma` `PostgreSQL` `LLaMA-Factory` `vLLM`

### [A General Solution Platform for CAE](https://github.com/ZPL-03/A-General-Solution-Platform-for-CAE)

开源 CAE 原型，使用 PyQt6 组织前后处理界面，Gmsh 负责参数化几何与网格，VTK/PyVista 负责结果显示，C++17/Eigen 实现求解核心，pybind11 暴露 Python 接口。当前项目覆盖四面体/六面体网格及线性、非线性和模态分析链路。

`C++17` `Eigen` `pybind11` `PyQt6` `Gmsh` `VTK/PyVista` `CMake`

### [航空复合材料多层级智能设计平台](https://github.com/ZPL-03/AC-GPT)

把微结构、层合板、加筋结构等层级的参数化建模、性能代理和轻量化优化放入统一桌面平台，并提供材料管理、模型加载与用户数据微调入口。

`Python` `PyQt6` `TensorFlow` `PyTorch` `NumPy/SciPy` `Visualization`

### Abaqus RVE 工具链

[2D RVE](https://github.com/ZPL-03/2D_RVE_Script) · [3D RVE](https://github.com/ZPL-03/3D_RVE_Script) · [3D RVE with Voids](https://github.com/ZPL-03/3D_RVE_Script_With_Viods) · [Short-fiber RVE](https://github.com/ZPL-03/3D_RVE_Script_SFRC_MP-PBC)

面向单向连续纤维、孔隙缺陷和随机短纤维微结构的 Abaqus 参数化建模脚本，覆盖随机纤维分布、周期镜像、干涉检查、材料与界面定义、网格划分、周期性边界条件和几何数据导出。

## AI 加速仿真 / AI-Accelerated Simulation

### FE-NN-KT 多尺度本构代理

```text
Abaqus RVE 参数化与 PBC
  -> 批量离线采样
  -> 粗网格源域预训练
  -> 细网格目标域迁移微调
  -> 神经网络预测一阶 Piola 应力 P
  -> 自动微分计算一致切线 A
  -> Q4 平面应变有限元与 Newton-Raphson 求解
  -> 与 Abaqus DNS 对照
```

代理模型替换积分点处的直接 RVE 求解，宏观平衡方程仍由有限元迭代求解。相对全细网格采样，离线高保真数据成本约降低 3.3 倍；在线宏观分析相对 DNS 达到约 20 倍量级加速。

### 微结构敏感横向失效准则

使用 ResNet-101 编码随机纤维微结构，将材料体系和微结构分布修正引入 Tsai-Wu 准则，并用 ICNN 约束失效包络的几何性质。该方法只使用四类基础载荷工况构建完整横向失效包络，对应论文发表于 *Thin-Walled Structures*。

### 物理约束渐进损伤响应预测

CNN 编码微结构，MLP 编码材料参数，LSTM 表示加载历史；训练目标同时考虑数据误差、初始刚度、峰后刚度软化和能量耗散，用于预测单轴/双轴工况下的应力应变曲线。

### 图网络全场代理原型

将 FEM 网格映射为节点和边组成的图，通过 Graph Transformer 聚合多跳结构信息，再由节点级解码器输出场变量。当前可核验范围为面向加筋壁板屈曲模态位移场的 Phase A 原型。

## 工程与实习经历 / Experience

| 时间 | 经历 | 工作重点 |
| --- | --- | --- |
| 2026.07-2026.09 | 华为技术有限公司，算法实习生 | AI 建模辅助：Pro/TOOLKIT C++ 开发 Creo 进程内 DLL，负责模型解析与 Top-3 交互；Python Worker 负责推理与缓存 |
| 2025.09-2026.06 | 北京神舟航天软件技术股份有限公司，研发实习生 | 开源 CAE 软件架构、复合材料多层级智能设计平台、积分点本构代理和网格级场代理探索 |
| 2025.09-2026.06 | 横向课题 | 复合材料结构领域 LLM、专家问答系统和多智能体智能设计系统 |
| 2023.11-2026.05 | 纵向课题 | RVE/层合板/加筋壁板高保真参数化建模求解、用户子程序、性能正向预测与逆向轻量化优化设计 |

## 论文与成果 / Publications & Outputs

### 已发表论文

1. **Liu Z**, Wang Q, Li Z, et al. [A model and data-driven transverse failure criterion for UD-CFRP composites by considering microstructure distribution and material variation](https://doi.org/10.1016/j.tws.2026.114751). *Thin-Walled Structures*, 2026, 114751. 第一作者。
2. Wang Q, Li Z, **Liu Z**, et al. [Interpretable prediction of ultimate strength of composite pressure hulls using data-driven symbolic regression](https://doi.org/10.1016/j.compositesa.2026.109863). *Composites Part A: Applied Science and Manufacturing*, 2026, 207: 109863. 第三作者。

### 知识产权

- 一种基于多智能体协同与领域大模型增强的复合材料压力壳结构智能设计系统，专利在投，第一发明人。
- 航空复合材料多层级智能设计平台 V1.0 (2026R11L0903472 | 第一完成人)。
- 复合材料参数化建模 Abaqus 插件 V1.0 (2026SR0649202 | 第一完成人)。
- 通用 CAE 求解系统 V1.0 (2026SR0649266 | 第一完成人)。
- Neper-PFC 数据转化接口 V1.0 (2023SR1283601 | 第一完成人)。

## 技术栈 / Tech Stack

| 领域 | 技术 |
| --- | --- |
| 力学仿真 / 建模 | Abaqus、ANSYS、Creo、SolidWorks |
| ML / DL | PyTorch、TensorFlow、Scikit-learn、DNN、CNN、GNN、RNN、ICNN、DeepONet、PINN、迁移学习 |
| LLM / Agent | PEFT、LLaMA-Factory、vLLM、Ollama、LangChain、LangGraph、RAG、ChromaDB、Neo4j |
| CAE开发 | Python、C++17、Fortran、CMake、Eigen、pybind11、MKL、OpenMP、MPI、CUDA/cuSPARSE、Gmsh、VTK、OpenCASCADE |
| 全栈开发 | Next.js 14、React、TypeScript、Zustand、Prisma、PostgreSQL、Cytoscape.js、Vercel、Cloudflare |

## 代表性荣誉 / Selected Awards

- 国家奖学金，优秀研究生。
- 2023 MCM/ICM M 奖，前 6%。
- 华为杯研究生数学建模竞赛二等奖，前 13%。
- 全国大学生数学竞赛二等奖。
- 数学、力学、数学建模和 AI 行业应用竞赛累计获奖 20 余项。

## 合作方向 / Collaboration Interests

- Abaqus 参数化建模脚本、用户子程序。
- 面向材料与结构响应的代理模型（正向预测/逆向设计）。
- LLM 后训练、RAG、知识图谱与工程 Agent 应用开发。
- 工业 AI 算法开发。

## 联系方式 / Contact

- GitHub: [@ZPL-03](https://github.com/ZPL-03)
- Online project: [CSGPT](https://csgpt.ipen03.com)
- Email: [lzp03@stu.xjtu.edu.cn](mailto:lzp03@stu.xjtu.edu.cn)
