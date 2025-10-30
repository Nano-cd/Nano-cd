<div align="center">

[ 简体中文 ](README_zh.md)

# Di Cheng (程地)

**Algorithm Engineer | Intelligent Systems Architect**

<p>From pixels and signals to language — I build elegant and efficient intelligent solutions for real-world challenges.</p>

<p>
  <a href="mailto:your.email@example.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="your_linkedin_url"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://ieeexplore.ieee.org/author/37086383618"><img src="https://img.shields.io/badge/IEEE-00629B?style=for-the-badge&logo=ieee&logoColor=white" /></a>
</p>

</div>

---

## 🚀 Selected Works

### 🏭 Industry Applications & Deployed Systems

*   **Fully Automated Medical Vision Inspection System (2024)**
    > Led the end-to-end development from algorithm selection to high-performance C++/ONNX deployment, including hardware integration. The system achieves **99%** detection accuracy and is stably running on multiple production lines.
    <details>
    <summary>📜 <b>Click to view System Architecture & Algorithm Details</b></summary>

    *   **System Architecture:** 
        1.  **Image Acquisition:** C++ SDK controls industrial cameras and syncs with LED light sources.
        2.  **Preprocessing:** OpenCV is used for image enhancement (e.g., contrast stretching, white balance).
        3.  **Model Inference:** PyTorch models are converted to ONNX and deployed in a C++ environment using ONNX Runtime for high performance.
        4.  **Post-processing & Output:** Morphological operations are applied to segmentation masks to reduce noise. Results are then formatted and delivered via a business logic interface.

    *   **Algorithm Details:**
        - **Model Selection:** A two-stage strategy was adopted: a lightweight **YOLOv8-n** for fast object localization, followed by **U-Net** for precise pixel-level segmentation within the ROI.
        - **Data Augmentation:** Custom augmentation strategies tailored for microscopic images, including random rotations, affine transforms, and simulated lighting variations.
        - **Loss Function:** A combination of **Dice Loss + Focal Loss** was used to effectively address class imbalance and small object segmentation challenges.
    </details>

*   **Signal Quality Optimization for Biochemical Analyzers (2025)**
    > Optimized core algorithms for clog detection, bubble detection, and two-point calibration. This data-driven approach reduced the equipment failure rate by **30%** and enabled early-warning for anomalies.
    <details>
    <summary>📜 <b>Click to view System Architecture & Algorithm Details</b></summary>

    *   **System Architecture:** 
        1.  **Data Ingestion:** Real-time/batch fetching of raw sensor data streams (pressure, optical signals) from the device database via SQL.
        2.  **Signal Processing Pipeline:** Built with Python (Pandas, NumPy) for filtering, noise reduction, and feature extraction.
        3.  **Multi-Algorithm Module:** Parallel execution of multiple detection algorithms.
        4.  **Decision & Alerting:** Fused outputs from all modules to generate diagnostic reports and trigger system alerts.

    *   **Algorithm Details:**
        - **Clog Detection:** Utilized **statistical features (mean, variance, kurtosis within a sliding window)** and template matching on time-series pressure data to detect anomalies.
        - **Bubble Detection:** Applied **high-pass filtering and peak detection** on optical signals to precisely identify transient dips caused by micro-bubbles.
        - **Two-Point Calibration:** Implemented **weighted non-linear fitting** to correct sensor drift across different concentrations, ensuring result accuracy and consistency.
    </details>

*   **Intelligent Consumable Management System (2025)**
    > An object detection-based system for automated identification and status monitoring of lab consumables, featuring a Gradio interface and a remote-callable API. Achieved **99%** detection rate.
    <details>
    <summary>📜 <b>Click to view System Architecture & Algorithm Details</b></summary>

    *   **System Architecture:** 
        1.  **Dynamic ROI Localization:** An initial "Workspace Analysis" algorithm automatically locates the consumable tray to eliminate background interference.
        2.  **Object Detection:** The detection model runs within the identified ROI to identify the type and count of consumables.
        3.  **Status Analysis:** The system determines the consumable status ("in-place", "missing", "in-use") based on changes in bounding box positions and counts.
        4.  **API Service:** A Gradio interface for quick demos and a C++ encapsulated RESTful API for integration with upstream systems.

    *   **Algorithm Details:**
        - **Workspace Analysis:** Leveraged **OpenCV's HSV color space conversion and contour finding** to robustly locate the workspace tray.
        - **Model Optimization:** Chose a lightweight **YOLOv5s** model and applied **INT8 quantization** to significantly boost inference speed on edge devices while maintaining accuracy.
        - **Robustness Design:** Trained the model on diverse data (various lighting, angles, occlusions) and used an **optimized NMS (Non-Maximum Suppression) threshold** to enhance performance in complex scenes.
    </details>

---

### 🔬 Research & Open Source Projects

*   **🩺 Medical Q&A Large Language Model (LoRA Fine-tuning) (2025)**
    > Fine-tuned the Qwen-1.5B model using LoRA and a medical SFT dataset. The model's accuracy on professional medical Q&A tasks improved by **15%**.
    > <br>➥ **[View Code](https://github.com/Nano-cd/deepseek-lora-medical)**

*   **📈 LLM-based Industrial Signal Anomaly Detection (2025)**
    > An innovative approach using a Large Language Model (`DeepSeek-R1`) as a feature extractor for industrial time-series data, complete with a Gradio interface.
    > <br>➥ **[View Code](https://github.com/Nano-cd/LLM_Detection)**

*   **🧠 Enhanced DIFnet with Gating and Hybrid Features (2025)**
    > Improved upon DIFnet by incorporating a gating mechanism and multi-scale feature fusion, boosting performance on image description and quality assessment tasks by **8% and 12%** respectively.
    > <br>➥ **[View Code](https://github.com/Nano-cd/difDLnet)**

*   **🏆 Image Quality Assessment (IQA) Research Series (2022-2023)**
    > Proposed several novel methods for IQA, with 3 papers accepted by top-tier computer vision conferences/journals. All code and datasets are open-sourced.
    > <br>➥ **[SSL-IQA (TMM'22)](https://github.com/Nano-cd/SSL_IQA)** | **[Paper Link](https://ieeexplore.ieee.org/abstract/document/9903545)**
    > <br>➥ **[DML-IQA (ICIP'22)](https://github.com/Nano-cd/DML_IQA)** | **[Paper Link](https://ieeexplore.ieee.org/abstract/document/9897784)**
    > <br>➥ **[Endoscopy Dataset (TCSVT'23)](https://ieeexplore.ieee.org/abstract/document/10078370)**
    
---

## 🛠️ My Toolkit

#### **Languages & Data Processing**
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?style=for-the-badge&logo=mathworks&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)

#### **Deep Learning & Frameworks**
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-FFD21E?style=for-the-badge)

#### **Deployment & Tools**
![ONNX](https://img.shields.io/badge/ONNX-00599C?style=for-the-badge&logo=onnx&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Gradio](https://img.shields.io/badge/Gradio-FF7C00?style=for-the-badge)
![Git](https://img.shields.io/badge/GIT-E44C30?style=for-the-badge&logo=git&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

---

<div align="center">

[![Nano-cd's GitHub stats](https://github-readme-stats.vercel.app/api?username=Nano-cd&show_icons=true&theme=tokyonight)](https://github.com/anuraghazra/github-readme-stats)

</div>
