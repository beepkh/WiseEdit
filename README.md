<h1 align="center" style="line-height: 50px;">
  WiseEdit: Benchmarking Cognition- and Creativity-Informed Image Editing
</h1>

<div align="center">

Kaihang Pan<sup>1</sup>\* · Weile Chen<sup>1</sup>\* · Haiyi Qiu<sup>1</sup>\* · Qifan Yu<sup>1</sup> · Wendong Bu<sup>1</sup> · Zehan Wang<sup>1</sup> ·  
Yun Zhu<sup>2</sup> · Juncheng Li<sup>1</sup> · Siliang Tang<sup>1</sup>  

<sup>1</sup>Zhejiang University &nbsp;&nbsp;&nbsp; <sup>2</sup>Shanghai Artificial Intelligence Laboratory  

\*Equal contribution.

[![arXiv](https://img.shields.io/badge/arXiv-2512.00387-b31b1b.svg)](https://www.arxiv.org/abs/2512.00387)
[![Project Page](https://img.shields.io/badge/Home-Page-b3.svg)](https://qnancy.github.io/wiseedit_project_page/)
[![Dataset](https://img.shields.io/badge/🤗%20Huggingface-WiseEdit_dataset-yellow)](https://huggingface.co/datasets/YourName/WiseEdit)
[![Code](https://img.shields.io/badge/GitHub-Code-181717?logo=github)](https://github.com/beepkh/WiseEdit)

</div>

---

# 🌍 Introduction

WiseEdit is a knowledge-intensive benchmark for cognition- and creativity-informed image editing. It decomposes instruction-based editing into three stages, **Awareness**, **Interpretation**, and **Imagination**, and provides **1,220 bilingual test cases** together with a GPT-4o–based automatic evaluation pipeline. Using WiseEdit, we benchmark **22 state-of-the-art image editing models** and reveal clear limitations in knowledge-based reasoning and compositional creativity.  

<p align="center">
  <img src="figures/intro.png" width="100%">
</p>

# 🔥 News

- **[2025.11.29]** 📄 WiseEdit paper released on arXiv.  
- **[2025.11.29]** 📊 WiseEdit project page released.
- More updates coming soon – stay tuned and ⭐ star the repo!

### TODO

- [x] Release paper and project page.  
- [ ] Release WiseEdit benchmark data(in one week).  
- [ ] Release automatic evaluation code & prompts(in one week).  
- [ ] Release baseline results & model outputs(coming soon).  

# 💡 Overview

WiseEdit is built around **task depth** and **knowledge breadth**.
<p align="center">
  <img src="figures/wiseedit-intro.png" width="90%">
</p>

## Task Depth – Four Task Types

WiseEdit includes: 

- **Awareness Task**  
  - Focus: *Where* to edit.  
  - No explicit spatial coordinates are given in the instruction.  
  - Requires comparative reasoning, reference matching, or fine-grained perception  
- **Interpretation Task**  
  - Focus: *How* to edit at the perception level.  
  - Instructions often encode **implicit intent**, demanding world knowledge  
- **Imagination Task**  
  - Focus: subject driven creative generation.  
  - Requires complex composition and identity-preserving transformations  

- **WiseEdit-Complex**  
  - Combines Awareness + Interpretation + Imagination.  
  - Multi-image, multi-step reasoning with conditional logic and compositional generation.

## Knowledge Breadth – Three Knowledge Types

WiseEdit organizes cases by **knowledge type**: 

- **Declarative Knowledge** – “knowing what”  
  - Facts, concepts, perceptual cues.  

- **Procedural Knowledge** – “knowing how”  
  - Multi-step skills or procedures.  

- **Metacognitive Knowledge** – “knowing about knowing”  
  - When and how to apply declarative / procedural knowledge; conditional reasoning, rule stacking, etc.  

These are grounded in **Cultural Common Sense**, **Natural Sciences**, and **Spatio-Temporal Logic**, stressing culturally appropriate, physically consistent, and logically coherent edits.

# ⭐ Evaluation Protocol

We adopt a **VLM-based automatic evaluation pipeline**:

- **Backbone evaluator**: GPT-4o (other VLMs also studied in the paper).  
- **Metrics (1–10 → linearly mapped to 0–100)**:   
  - **IF** – Instruction Following  
  - **DP** – Detail Preserving  
  - **VQ** – Visual Quality  
  - **KF** – Knowledge Fidelity (for knowledge-informed cases)  
  - **CF** – Creative Fusion (for imagination / complex cases)  

The **overall score** is:
$\text{AVG} = \frac{\text{IF} + \text{DP} + \text{VQ} + \alpha \cdot \text{KF} + \beta \cdot \text{CF}}{3 + \alpha + \beta}$

where $\alpha$ and $\beta$ are 1 only when KF / CF are applicable.
Our user study shows strong correlation between this protocol and human ratings.  


# 🚀 Usage
coming in one week!

# ✍️Citation

If you find WiseEdit helpful, please cite:
```bibtex
@misc{pan2025wiseeditbenchmarkingcognitioncreativityinformed,
      title={WiseEdit: Benchmarking Cognition- and Creativity-Informed Image Editing}, 
      author={Kaihang Pan and Weile Chen and Haiyi Qiu and Qifan Yu and Wendong Bu and Zehan Wang and Yun Zhu and Juncheng Li and Siliang Tang},
      year={2025},
      eprint={2512.00387},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2512.00387}, 
      }
```



