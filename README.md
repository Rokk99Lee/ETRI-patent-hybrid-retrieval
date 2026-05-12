# ETRI-patent-hybrid-retrieval: Evaluation Data
Replication data and supplementary materials for the paper "Hybrid Retrieval Outperforms Domain-Specific Fine-Tuning for Patent Document Search: A Large-Scale Empirical Study"

## Contents

The repository provides the following materials, organized into year-based folders (2005, 2015, 2025):

- **Generated evaluation queries**: 9,450 queries in total (1,050 sampled patents × 3 query types × 3 years). Three query types are provided for each sampled patent: summary, keyword, and function queries.
- **Ground-truth sample patent data**: The 1,050 sampled patents per year that serve as ground truth for the corresponding evaluation queries.

## Source Patent Corpus

The full corpus of 674,732 USPTO granted patents from 2005, 2015, and 2025 used in the retrieval experiments is not included in this repository due to its size. The original patent data is publicly available from the United States Patent and Trademark Office at:

https://data.uspto.gov/support/transition-guide/patentsview

The corpus can be reconstructed by downloading the granted patent records for the corresponding years from the link above. The sampled patents provided in this repository (`sample_patents.csv` files) are drawn from this corpus and include the patent identifiers needed to align with the original USPTO records.

## Query Generation

The evaluation queries were generated using an open-weight large language model (gpt-oss-20b, deployed locally via Ollama). A multi-stage lexical leakage prevention protocol, including prompt-level paraphrase encouragement, automated 3-gram overlap detection, forbidden n-gram injection, and iterative regeneration with progressive temperature increase, was applied during query generation. Full methodological details are provided in Section 3.2 and Appendix A of the manuscript.
