Exploring Semantic Structure and Bias in Word Embeddings

## Overview

This project investigates how pretrained word embeddings encode semantic relationships and social bias in high-dimensional vector space. Using Word2Vec, GloVe, and fastText models, I analyze cosine similarity, analogy performance, gender–profession associations, and geometric clustering through dimensionality reduction.

The goal of this project is to understand how language can be represented mathematically — and how these representations connect to modern transformer architectures.

## Motivation

Word embeddings were one of the first breakthroughs that allowed natural language to be modeled using dense linear algebra rather than sparse symbolic features.

Understanding static embeddings helps answer key questions:

- How does a model represent meaning numerically?
- Why does vector arithmetic work for analogies?
- How does bias enter machine learning systems?
- Why did transformer models move toward contextual embeddings?

This project bridges foundational NLP techniques with modern large language model design.

## Methods
1️⃣ Pretrained Embedding Models

The following models were loaded using gensim:

- Word2Vec (Google News, 300d)
- GloVe (Wikipedia + Gigaword, 100d)
- fastText (Wikipedia, subword modeling, 300d)

2️⃣ Semantic Similarity

Cosine similarity was used to explore nearest neighbors for selected words such as:

king
computer
doctor

This demonstrates how embeddings organize semantic neighborhoods.

3️⃣ Analogy Experiments

Vector arithmetic was used to test analogies such as:

king − man + woman ≈ queen
paris − france + germany ≈ europe
good − better + bad ≈ worse

These experiments illustrate how relationships form consistent linear directions in embedding space.

4️⃣ Bias Analysis

To explore gender bias:

A gender direction vector was constructed:
woman − man

Profession vectors were projected onto this direction.

Results reveal systematic associations such as:
nurse, receptionist → female-aligned direction
engineer, manager → male-aligned direction

This demonstrates how embeddings encode societal patterns present in training data.

5️⃣ Model Comparison

Word2Vec, GloVe, and fastText were compared on analogy tasks.

Key observation:

fastText performs better on morphology-related tasks due to subword modeling.
Word2Vec and GloVe rely on whole-word representations.
Model architecture influences embedding behavior.

6️⃣ Visualization

Principal Component Analysis (PCA) was used to reduce embeddings from 300 dimensions to 2 dimensions.

Clusters observed:

Royal terms (king, queen, prince)
Gender-related words
Countries and capitals
Profession groupings

Although dimensionality reduction distorts distances, it provides geometric intuition for semantic structure.

## Key Results

Semantic similarity corresponds to geometric proximity.
Analogical reasoning emerges from linear vector relationships.
Gender bias appears as measurable directional alignment.
Model architecture affects representation quality.
Static embeddings are limited compared to contextual transformer embeddings.

### Example Outputs

Below are selected visualizations generated in this project:

- PCA embedding clusters (`outputs/pca_embedding_clusters.png`)
- Gender bias projection chart (`outputs/gender_bias_projection.png`)
- Cosine similarity heatmap (`outputs/similarity_heatmap.png`)

## Limitations

Each word has only one vector representation (no context awareness).

Polysemy (e.g., “bank”) cannot be disambiguated.
Bias present in the training corpus is directly encoded.
PCA visualization simplifies high-dimensional structure.
Modern transformer models address these limitations by producing contextual embeddings via attention mechanisms.

## Connection to Transformers

Transformer models begin with embedding layers similar to Word2Vec/GloVe, but instead of assigning one fixed vector per word, they dynamically update representations using self-attention.

For example:

“bank” in river bank and open a bank account receives different contextual embeddings.

Static embeddings were foundational to NLP, but transformers extend them into context-sensitive representations.

## Repository Structure

PORTFOLIO-PIECE-1-MUSKAANGUPTA20/
├── README.md
├── requirements.txt
├── notebooks/
│   └── main_analysis.ipynb
├── outputs/
│   └── embedding_visualizations.png

## How to Run

Clone the repository:

git clone <https://github.com/bu-cds-llms/reflections-and-labs-muskaangupta20.git>
cd [https://github.com/bu-cds-llms/reflections-and-labs-muskaangupta20.git]

## Install dependencies:

pip install -r requirements.txt

Run the notebook:

Open notebooks/main_analysis.ipynb

Execute all cells

Note: Pretrained embedding models will download automatically via gensim.

## Requirements

Python 3.9+
gensim
numpy
matplotlib
scikit-learn
pandas

## Learning Reflection

Through this project, I gained a deeper understanding of how language models represent meaning using linear algebra. Observing semantic clustering and bias directly in vector space made abstract lecture concepts concrete.

This work strengthened my intuition for why embeddings were such a major milestone in NLP — and why transformers build upon them rather than replacing them entirely.