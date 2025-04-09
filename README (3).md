# REST: Graph-Based Residual State Update Mechanism for Real-Time EEG Analysis

## Overview
REST (Residual EEG State Tracker) is a novel deep learning framework that models EEG signals as temporal graphs, using Graph Neural Networks (GNNs) combined with residual state updates. It is designed for real-time seizure detection and classification, capturing both spatial and temporal dependencies within EEG recordings.

## Key Features
- Graph-based modeling of EEG electrode connectivity
- Residual State Update module for efficient sequence learning
- RNN-based temporal modeling of node representations
- Real-time seizure detection and classification

---

## Project Architecture

![Model Architecture](https://raw.githubusercontent.com/arshiaafzal/REST/main/images/model_architecture.png)

**Figure:** REST integrates dynamic graph structures with GNN layers and residual RNN blocks to capture spatial and temporal EEG dynamics.

---

## Dataset

### 1. CHB-MIT Scalp EEG Database
- Pediatric scalp EEG dataset with seizure annotations
- Sampling frequency: 256 Hz
- 23 patients
- 10–20 system electrode placement

### 2. TUH EEG Seizure Corpus
- World's largest open-source EEG dataset
- Multi-class seizure labels
- Adult and pediatric subjects
- Rich annotations for real-time applications

---

## Results

### Seizure Detection Accuracy (Binary Classification)

| Model        | Accuracy (%) | F1 Score | AUC-ROC |
|--------------|--------------|----------|----------|
| CNN-LSTM     | 89.2         | 0.88     | 0.91     |
| EEGNet       | 90.5         | 0.90     | 0.92     |
| **REST (Ours)** | **93.7**     | **0.93** | **0.95** |

### Inference Speed

| Model        | Inference Time (ms/sample) |
|--------------|----------------------------|
| EEGNet       | 13.5                       |
| CNN-LSTM     | 19.2                       |
| **REST (Ours)** | **11.8**                     |

---

## Installation
```bash
git clone https://github.com/arshiaafzal/REST.git
cd REST
pip install -r requirements.txt
```

---

## Usage
```bash
python train.py --dataset tuh
```

You can change `--dataset` to `chbmit` for the CHB-MIT EEG dataset.

---

## Visualizations

![EEG Graph Construction](https://raw.githubusercontent.com/arshiaafzal/REST/main/images/graph_construct.png)

**Figure:** EEG channels modeled as graph nodes with edge weights based on functional connectivity (e.g., Pearson correlation).

![Loss Curves](https://raw.githubusercontent.com/arshiaafzal/REST/main/images/loss_curve.png)

**Figure:** Training vs validation loss showing model convergence.

---

## Author
**Nidhish Chettri**  
B.Tech, Maharaja Agrasen Institute of Technology  
Email: nidhishchettri@gmail.com

---

## Acknowledgements
- Temple University Hospital for TUH EEG Corpus
- MIT for CHB-MIT dataset
- [Original REST Paper](https://arxiv.org/abs/2303.09415)

---

## License
This project is licensed under the MIT License.