# Initial Retrieval Module
The Initial Retrieval module is the first stage of the two-stage fine-grained sub-element retrieval framework. It aims to narrow down the candidate printed fabric images by extracting global features and performing a rough ranking, providing a basis for the subsequent re-ranking stage with query-guided attention.
# Overview
In the fine-grained sub-element retrieval task for printed fabrics, directly processing all images with complex attention mechanisms can be computationally expensive. The initial retrieval module addresses this by:

1. Extracting robust global features from fabric images and query sub-elements.

2. Computing similarity between query sub-elements and fabric images based on global features.

3. Generating a preliminary ranking of candidate images, significantly reducing the number of candidates for subsequent refinement.

This stage lays the foundation for efficient and accurate retrieval by filtering out irrelevant images early, ensuring the re-ranking stage focuses only on high-potential candidates.
# Usage
1. Prepare Data and Weights
   
   -Dataset: Download the `SimulatedPrintedFabrics-17k` and `RealPrintedFabrics-13k` datasets from https://www.kaggle.com/datasets/yunjiaoma/finegrainedsubelementretrievaldataset.
   
   -Pre-trained Weights: Download the `dinov2-pytorch-base-v1` into `Weight_Path/`.

2. Configure Parameters

   Modify the key parameters in the Jupyter notebook.
   
3. Run Initial Retrieval

   -Execute the `Dinov2_finetuning_training.ipynb` to start initial retrieval.

   -Execute the `Dinov2_finetuning_evaluate.ipynb` to evaluate the training progress.

   -Execute the `Candidate_pool_generation.ipynb` to generate retrieval candidates.

# Output
The initial retrieval results are saved in Output/, with the following structure:

-`query_path`: Path to the query sub-element.

-`image_path`: Path to the candidate fabric image.

-`similarity`: Global feature similarity score.

This output file is directly used as input for the `Reranking` module to perform fine-grained refinement.
