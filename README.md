# HarmonYǎ – Hybrid Music Recommendation System 
<img src="https://github.com/ologiaeskander/HarmonYa/blob/main/assets/Logo_back.png?raw=true" height="100"/>

HarmonYǎ is a modular, scalable music recommendation system that combines collaborative filtering (CF) and content-based filtering (CBF) to deliver personalized, cold-start-resilient track recommendations. It also suggests a proof of concept unified content aware collaborative filtering model architecture.

> This project was developed as a graduation project to explore intelligent, and extensible recommender architectures that balance user taste and audio semantics.

---

## Project Overview

HarmonYǎ is built on a two-tower architecture:

- **Collaborative Filtering Tower**: Learns from playlist-track co-occurrence using a gated neural embedding model
- **Content-Based Filtering Tower**: Uses 13-dimensional audio feature vectors and Annoy for nearest-neighbor retrieval
- **Hybrid Fusion Layer**: Dynamically combines CF and CBF outputs based on data availability and playlist length

![Two-Tower Model](https://github.com/ologiaeskander/HarmonYa/blob/main/assets/Two%20Tower%20Model.drawio.png?raw=true)

---

## Key Features

- Modular architecture for easy experimentation and research
- Robust handling of cold-start scenarios with CBF fallback
- Precision-focused CF model with temperature-scaled dot-product scoring
- Efficient approximate nearest neighbor search using Annoy
- Dynamic hybrid weighting based on playlist metadata
- URI ↔ index mapping for seamless model-to-Spotify communication

---

## Notebooks & Demos

- `two_tower_hybrid_arch.py`: Complete hybrid recommender implementation with CF + CBF fusion
- `true_hybrid_model.py`: Experimental unified content-aware collaborative filtering model (proof-of-concept only)
<!-- - [Colab Demo Notebook](link-here): Run the hybrid model on training-set playlists (index-mapped) -->

> Current model input is limited to known training playlists due to internal index mapping. Generalization requires future retraining with decoupled inputs.

---

## Datasets Used

- [Million Playlist Dataset](https://www.kaggle.com/datasets/notshrirang/spotify-million-song-dataset) (MPD) – playlist-track interactions
- [1.2M Songs Dataset (Kaggle)](https://www.kaggle.com/datasets/rodolfofigueroa/spotify-12m-songs) – audio features
- [Spotify Tracks DB](https://www.kaggle.com/datasets/zaheenhamidani/ultimate-spotify-tracks-db)

Due to low overlap (~8.6%), the unified model uses synthetic audio vectors for training feasibility.

---

<!-- ## 📂 Repository Structure

```bash
├── models/             # Saved model files (.keras, .pkl, Annoy index)
├── src/                # Training, inference, evaluation code
├── demo/               # Colab notebook(s)
├── data/               # Sample data snippets / preprocessing tools
├── unified_model/      # Architecture for single-model hybrid recommender
└── README.md           # You're here! -->
