# Fine-Grained-Sub-Element-Retrieval-in-Printed-Fabrics-via-Query-Guided-Attention
This repository contains the implementation of the paper **《Fine-Grained Sub-Element Retrieval in Printed Fabrics via Query-Guided Attention》**.
# Overview
Accurate fine-grained image retrieval is a critical challenge in pattern recognition, especially in industrial scenarios where local semantic alignment is essential. This work focuses on the specific task of retrieving printed fabric images based on a query sub-element (e.g., a specific pattern or motif), which is a demanding case of pattern search and matching.
Existing methods relying on global features often fail to capture fine-grained local semantics, limiting their performance in distinguishing fabrics with similar overall appearances but varying sub-element details. To address this gap, we propose a novel two-stage retrieval framework centered on a query-guided attention mechanism. The overall framework is depicted in Fig.1.
![Proposed ](img/Framework5.tiff "network architecture")
Printed fabric images are usually composed of multiple sub-elements, such as Elements #1 to #5 illustrated in the figure. Taking Element #3 as an example, the retrieval procedure for identifying printed fabric images containing this sub-element employs a two-stage strategy.
1. **Initial Retrieval**: Narrow down candidate images using global features to obtain a rough ranking.
2. **Re-ranking**: Refine the initial results by dynamically highlighting the sub-element details while suppressing irrelevant background patterns via the query-guided attention mechanism.
**Experimental Results**: The proposed method demonstrates superior performance, achieving a mean average precision (mAP) of 81.95% on the Oxford5k benchmark and 89.34% on the Paris6k benchmark, outperforming several state-of-the-art approaches. Additionally, validation on a real printed fabric dataset confirms its strong industrial applicability and potential to improve production workflows. The retrieval results of RealPrintedFabrics-13k are shown in Fig.2.
[Real Retrieval Results3.tif](https://github.com/user-attachments/files/23572472/Real.Retrieval.Results3.tif)
Fig. 2 Top 10 retrieval results of RealPrintedFabrics-13k
# Dataset
The dataset used in this project includes:
1. SimulatedPrintedFabrics-17k: a simulated dataset by mimicking printed fabric generation mechanisms for network training.
2. RealPrintedFabrics-13k: a collected real printed fabric image dataset for performance validation on the real world.
3. Public benchmarks: Oxford5k and Paris6k (for general fine-grained retrieval validation)
The proposed datasets (SimulatedPrintedFabrics-17k and RealPrintedFabrics-13k) can be accessed from https://www.kaggle.com/datasets/yunjiaoma/finegrainedsubelementretrievaldataset.
# Repository Structure
Fine-Grained-Sub-Element-Retrieval-in-Printed-Fabrics-via-Query-Guided-Attention/
├── Initial_Retrieval/        # Module for initial retrieval (global feature extraction, rough ranking)
│   ├── Weight_Path/          # Pre-trained model weights storage
│   ├── Output/               # Initial retrieval results
│   └── [code files]          # Scripts for initial retrieval pipeline
├── Reranking/                # Module for re-ranking (query-guided attention refinement)
│   └── [code files]          # Scripts for re-ranking with attention mechanism
└── README.md                 # Project documentation
# Installation
Clone this repository:
git clone https://github.com/aha0818/Fine-Grained-Sub-Element-Retrieval-in-Printed-Fabrics-via-Query-Guided-Attention.git
cd Fine-Grained-Sub-Element-Retrieval-in-Printed-Fabrics-via-Query-Guided-Attention
# Usage
1. **Prepare the Dataset**
   Download the SimulatedPrintedFabrics-17k, RealPrintedFabrics-13k, Oxford5k, and Paris6k.
2. Initial Retrieval
   Run the initial retrieval to get a rough ranking of candidates. The usage details can be accessed from the Initial_Retrieval/README.md
3. Re-ranking with Query-Guided Attention
   Refine initial results using the attention mechanism. The usage details can be accessed from the Reranking/README.md
# Citation
If you use this code or dataset in your research, please cite our paper:
# Contact
For questions or issues, please contact: mamayunjiao@163.com.
