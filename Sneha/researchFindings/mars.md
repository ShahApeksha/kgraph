# MARS: Discovering Novel Cell Types across Heterogeneous Single-cell Experiments
MARS is a tool for identifying and annotating cell types across heterogeneous single-cell experiments.
MARS has a unique ability to discover and suggest human-interpretable names to novel cell types that
have never been seen in previously annotated experiments.
1. How are they collecting data?
- The document mentions several datasets that were used in the study, including Tabula Muris, Tabula Muris Senis, Pollen, Kolodziejczyk, CellBench, and AllenBrain.
- The number of annotated cells in each dataset is also provided.
- The datasets were publicly available and were preprocessed using scanpy and anndata packages.
- The code for MARS is available on GitHub and was written in Python using the PyTorch library. The source code is also available on GitHub.
- No specific details about the actual data collection process are provided. 
# End objective.
- The end objective of the MARS (Meta-Analysis of Single-cell RNA-Seq) method is to learn a joint embedding space for annotated and unannotated single-cell RNA sequencing experiments, where cells are mapped to the embedding space and grouped around cell-type landmarks.
- The objective function balances between intracluster minimization and intercluster maximization, and both parts are optimized within each experiment, allowing clusters across experiments to align with each other.
- The project also emphasizes the importance of data and code availability and includes acknowledgments and funding information.
# Note:
- It discusses the MARS method, which uses a deep neural network to map cells to a low-dimensional vector space and capture cell-type identity.
- The method also uses regularization and an objective function to learn a representation in which cells group close to their corresponding landmarks.
- The approach aims to harmonize heterogeneous and time-varying datasets,learn dataset-invariant cell representations, and use the learned representations to decide whether groups of measured cells represent previously uncharacterized cell types and cell states