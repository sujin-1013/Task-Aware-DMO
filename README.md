# Task-Aware-DMO

**Dynamic Model Optimization for Multi-Task Learning**  
📄 IEEE Access 2023 — [DOI: 10.1109/ACCESS.2023.3339793](https://doi.org/10.1109/ACCESS.2023.3339793)

This repository introduces the core ideas and implementation of  
**Task-Aware Dynamic Model Optimization (DMO)**, a memory-efficient multi-task learning (MTL) framework.


## 🔍 Overview

Multi-task learning (MTL) often suffers from **task interference** and **inefficient resource usage**.  
**DMO (Dynamic Model Optimization)** addresses these issues by:

- Grouping tasks based on **inter-task similarity** (weight & loss correlations)
- Dynamically allocating parameters based on **task difficulty**
- Producing **lightweight subnetworks**, reducing parameters by over **80%** on average

<p align="center">
  <img src="https://github.com/your-username/Task-Aware-DMO/raw/main/dmo_overview.png" width="700"/>
</p>

<sub><i>Figure: Overview of Task-Aware Dynamic Model Optimization framework</i></sub>

## 🎯 Key Components

- **Task Similarity Measurement**
  - Pearson correlation on weights (`S_W`)
  - Pearson correlation on losses (`S_L`)
- **Task Grouping**
  - Graph-based maximal clique detection (Bron–Kerbosch)
- **Dynamic Parameter Allocation**
  - Pruning by task difficulty
  - Merging into group-specific subnetworks


## 🛠️ Code Structure

- `models/`: Backbone network, task-specific heads, pruning utilities
- `train.py`: Training logic across grouped tasks
- `evaluate.py`: Evaluation and metrics
- `config/`: Experimental settings
- `results/`: Graphs and tables from the paper
- `paper/`: Original PDF paper for reference

## 🧪 Datasets Used

- CIFAR-10, STL-10, MNIST, USPS
- CIFAR-100 (20-task version)
- Visual Decathlon Challenge (10 diverse tasks)


## 📊 Result Summary

| Dataset Group         | Param Reduction | Accuracy (Avg)   |
|----------------------|-----------------|------------------|
| CIFAR-10 + MNIST     | ~84%            | ⭤ Comparable     |
| CIFAR-100 (20 Tasks) | ~85%            | ⬆️ Improved       |
| Decathlon Challenge  | ~88%            | ⭤ Slight Drop     |

> 🔹 Up to **97% reduction** on USPS with minimal performance loss


## 🧑‍💻 Author

Su-jin Choi (최수진)  
Master of AI, Chung-Ang University  
Email: [popo2419@naver.com]  
Paper DOI: [10.1109/ACCESS.2023.3339793](https://doi.org/10.1109/ACCESS.2023.3339793)

---

🔧 _Code under construction. More modules coming soon._
