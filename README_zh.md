<div align="center">

# 程地 (Cheng Di)

**算法工程师**

<p>从像素、信号到语言</p>

<p>
  <a href="mailto:chengdigogogo@outlook.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="https://www.linkedin.com/in/%E5%9C%B0-%E7%A8%8B-442023295/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://ieeexplore.ieee.org/author/37089721043"><img src="https://img.shields.io/badge/IEEE-00629B?style=for-the-badge&logo=ieee&logoColor=white" /></a>
</p>

</div>

---

## 🚀 精选作品 (Selected Works)

### 🏭 **产业应用 & 系统落地**

*   **全自动管型识别检测系统 (2024)**
    > 主导从算法选型到C++/ONNX高性能部署的全链路，集成相机与光源系统。系统检测准确率达 **99%**，已在多条产线及客户端稳定运行。
    <details>
    <summary>📜 <b>点击查看系统架构与算法细节</b></summary>

    *   **系统架构:** 
        1.  **图像采集:** C++ SDK调用工业相机，与LED光源系统同步曝光，获取高质量显微图像。
        2.  **预处理:** 使用OpenCV进行图像增强，如对比度拉伸、白平衡校正，突出管型特征。
        3.  **模型推理:** 将PyTorch训练的模型转换为ONNX格式，使用ONNX Runtime在C++环境中进行高性能推理。
        4.  **后处理与输出:** 对模型的分割Mask进行形态学操作（如开运算）去噪，计算管型数量与分类，并将结果通过业务逻辑接口输出。

    *   **算法细节:**
        - **模型选型:** 采用两阶段策略，先由轻量级的**YOLOv8-n**进行快速目标定位，再对ROI区域使用**U-Net**进行像素级精准分割，兼顾速度与精度。
        - **数据增强:** 针对显微图像特点，设计了包括随机旋转、仿射变换以及模拟不同光照条件的自定义数据增强策略。
        - **损失函数:** 采用**Dice Loss + Focal Loss**的组合损失函数，有效解决了样本类别不均衡和小目标分割难的问题。
    </details>

*   **生化检测设备信号质量优化 (2025)**
    > 负责改进堵针、气泡检测、两点标定等核心算法。通过数据驱动的优化，将设备故障率**降低30%**，并实现了异常信号的提前预警。
    <details>
    <summary>📜 <b>点击查看系统架构与算法细节</b></summary>

    *   **系统架构:** 
        1.  **数据接入:** 通过SQL从设备数据库实时/批量拉取传感器原始数据流（如压力、光耦信号）。
        2.  **信号处理流水线:** 使用Python (Pandas, NumPy) 构建信号处理管道，包括滤波、降噪、特征提取。
        3.  **多算法模块:** 并行运行堵针、气泡等多个检测算法模块。
        4.  **决策与报警:** 融合各模块输出，生成设备状态诊断报告，并通过系统接口触发报警。

    *   **算法细节:**
        - **堵针检测:** 基于时序信号的**统计特征（滑动窗口内的均值、方差、峰度）**与模板匹配，实时监测压力曲线的异常抬升或剧烈波动。
        - **液路气泡检测:** 利用**高通滤波与峰值检测算法**，捕捉光耦信号中的瞬时高频扰动，精准识别由微小气泡引起的信号下跌。
        - **两点标定算法:** 引入**带权重因子的非线性拟合**，修正传感器在不同浓度下的响应漂移，确保检测结果的准确性与一致性。
    </details>

*   **智能耗材管理检测系统 (2025)**
    > 基于目标检测，实现耗材的自动识别与状态监控。封装了Gradio可视化界面与远程调用API，耗材检出率达 **99%**。
    <details>
    <summary>📜 <b>点击查看系统架构与算法细节</b></summary>

    *   **系统架构:** 
        1.  **动态区域定位:** 首先运行“工作区域分析算法”，自动框定耗材架或工作台面，排除背景干扰。
        2.  **目标检测:** 在定位出的ROI内，运行目标检测模型，识别各类耗材的位置与数量。
        3.  **状态分析:** 根据检测框的位置、数量变化，判断耗材是“在位”、“缺失”还是“使用中”。
        4.  **接口服务:** 使用Gradio快速搭建可视化Demo，同时提供C++封装的RESTful API接口，供上层系统远程调用。

    *   **算法细节:**
        - **工作区域分析:** 利用**OpenCV的颜色空间转换(HSV)和轮廓查找(Contour Finding)**，快速稳定地定位颜色或形状特定的工作区域托盘。
        - **模型优化:** 选用轻量化的**YOLOv5s**模型，并进行**INT8量化**，在保证精度的前提下，大幅提升在边缘设备上的推理速度。
        - **鲁棒性设计:** 通过大量场景数据（不同光照、角度、遮挡）进行模型训练，并采用**NMS（非极大值抑制）**的优化阈值，提高复杂场景下的检测鲁棒性。
    </details>

---

### 🔬 **前沿研究 & 开源项目**

*   **🩺 医疗问答大模型 (LoRA 微调) (2025)**
    > 基于 Qwen-1.5B，使用 LoRA 技术对医疗SFT数据集进行参数高效微调。模型在专业问答任务上准确率**提升15%**。
    > <br>➥ **[查看代码](https://github.com/Nano-cd/deepseek-lora-medical)**

*   **📈 基于LLM的工业信号异常检测 (2025)**
    > 创新性地将大语言模型(`DeepSeek-R1`)作为特征提取器，用于工业时序信号分析，并搭建了Gradio可视化交互系统。
    > <br>➥ **[查看代码](https://github.com/Nano-cd/LLM_Detection)**

*   **🧠 DIFnet模型改进 (2025)**
    > 在DIFnet基础上，通过门控机制与多尺度特征融合，增强上下文信息，在图像描述和质量评估任务上性能分别**提升8%和12%**。
    > <br>➥ **[查看代码](https://github.com/Nano-cd/difDLnet)**

*   **🧬 AI胰腺癌智能诊断探索 (2025)**
    > 综合运用XGBoost, MLP, ResNet, LSTM, GNN, LLM等多种模型，对消化道肿瘤标志物进行多维度分析与预测，并利用SHAP、t-SNE进行模型可解释性分析。
    > <br>➥ `[项目报告]`

*   **🏆 图像质量评价(IQA)系列研究 (2022-2023)**
    > 针对图像质量评价领域提出多种创新方法，3篇成果均被计算机视觉顶会/顶刊接收，代码与数据集均已开源。
    > <br>➥ **[SSL-IQA (TMM'22)](https://github.com/Nano-cd/SSL_IQA)** | **[论文链接](https://ieeexplore.ieee.org/abstract/document/9903545)**
    > <br>➥ **[DML-IQA (ICIP'22)](https://github.com/Nano-cd/DML_IQA)** | **[论文链接](https://ieeexplore.ieee.org/abstract/document/9897784)**
    > <br>➥ **[内窥镜数据集 (TCSVT'23)](https://ieeexplore.ieee.org/abstract/document/10078370)**
    
*   **📡 基于多尺度非局部均值的PET图像去噪 (2020)**
    > 本科毕业设计。结合小波变换与非局部均值滤波，相较传统方法，PSNR **提升 2~3dB**。
    > <br>➥ `[查看论文]`

---

## 🛠️ 我的技术栈 (My Toolkit)

#### **语言 & 数据处理**
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?style=for-the-badge&logo=mathworks&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)

#### **深度学习 & 框架**
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-FFD21E?style=for-the-badge)

#### **部署 & 工具**
![ONNX](https://img.shields.io/badge/ONNX-00599C?style=for-the-badge&logo=onnx&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Gradio](https://img.shields.io/badge/Gradio-FF7C00?style=for-the-badge)
![Git](https://img.shields.io/badge/GIT-E44C30?style=for-the-badge&logo=git&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

---

<div align="center">

[![Nano-cd's GitHub stats](https://github-readme-stats.vercel.app/api?username=Nano-cd&show_icons=true&theme=tokyonight)](https://github.com/anuraghazra/github-readme-stats)

</div>
