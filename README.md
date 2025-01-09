# Enhancing Multimodal Learning with Knowledge Graphs

## Overview
This project integrates Knowledge Graphs (KGs) into multimodal models to improve accessibility-related tasks, particularly generating scene descriptions for visually impaired users. By combining image embeddings, KG embeddings, and a recurrent neural network, the model generates enriched image captions that capture situational understanding and object relationships, addressing accessibility challenges.

## Key Features
- **Knowledge Graph Integration**: Leverages KGs for contextual knowledge, enhancing model understanding of object relationships and situational context.
- **Multimodal Learning**: Combines image embeddings (from CLIP) and semantic embeddings (from ConceptNet) to improve contextual understanding in image captioning.
- **Accessibility Focus**: Evaluates performance on datasets like VizWiz-Captions, curated for real-world accessibility challenges.
- **Custom Decoding Techniques**: Employs modified beam search algorithms to minimize repetition and improve sentence structure in captions.

## Project Structure
- `data`: COCO and VizWiz-Captions datasets used for training and evaluation
- `embeddings`: Extracted image and KG embeddings using CLIP and ConceptNet
- `models`: Neural network architecture for combining embeddings and generating captions
- `evaluation`: Tools for evaluating model performance using BLEU-1, ROUGE-L, CIDEr, and SPICE metrics
- `results`: Outputs from the evaluation phase, including score histograms and qualitative comparisons

## Methodology
1. **Embedding Extraction**:
   - **Image Embeddings**: Utilized CLIP to encode images into high-dimensional vectors capturing visual and semantic details.
   - **KG Embeddings**: Used ConceptNet to encode captions into word embeddings, weighted by their importance using TF-IDF.
2. **Language Modeling**:
   - Unified image and KG embeddings into a shared latent space.
   - Employed a one-layer LSTM to predict captions in an autoregressive manner.
3. **Decoding**:
   - Modified beam search with heuristics for length normalization, repetition penalties, and trigram blocking to generate fluent captions.
4. **Datasets**:
   - Trained on COCO captions and evaluated on VizWiz-Captions, addressing real-world accessibility challenges.

## Results
- The model incorporating KGs outperformed the baseline across multiple metrics:
  - **BLEU-1**: Higher word-level matching accuracy, with statistically significant improvements.
  - **ROUGE-L**: Improved sentence structure alignment, though not statistically significant.
  - **SPICE**: Enhanced scene description accuracy.
  - **CIDEr**: The baseline scored higher due to greater diversity, but KG integration improved categorical accuracy.
- Qualitative analysis showed that KG integration led to more contextually relevant captions, though it introduced a bias towards common KG relationships.

## Contributions
- **Ananya Kulshrestha**: Developed the embedding integration pipeline, led evaluation efforts, and analyzed results.
- **Ethan Harbaugh**: Implemented language modeling components and assisted with KG embedding integration.
- **Julianna Schneider**: Focused on dataset preparation, decoding modifications, and visualization of results.

## Future Work
- Enhance model architecture with attention mechanisms for improved feature extraction.
- Train on diverse datasets to generalize performance across varied accessibility scenarios.
- Investigate the impact of KG biases on captioning accuracy and diversity.
- Expand evaluation to include user feedback for accessibility-focused metrics.

## Acknowledgements
Special thanks to Professor Andreas, Dr. Tanner, Dr. Maune, and the entire 6.8611 course staff for their invaluable guidance and support. Additional gratitude to the teams behind COCO and VizWiz-Captions datasets for making this research possible.

## References
For detailed citations and references, please see the full project report.
