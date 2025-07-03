# Car EchoFix 

**Car EchoFix** è un sistema di classificazione automatica dei guasti del motore basato su segnali audio. Il progetto sfrutta tecniche di *audio preprocessing*, *data augmentation* e *deep learning* per analizzare i suoni del motore e identificare sei diverse condizioni operative, con l’obiettivo di supportare la diagnosi predittiva nel settore automotive.

---

## 📁 Dataset

Il dataset utilizzato è [AI Mechanic: Engine Condition Audio Fault Finding](https://www.kaggle.com/datasets/eoinedge/ai-mechanic-engine-condition-audio-fault-finding), disponibile su Kaggle, contenente registrazioni audio annotate di motori in diverse condizioni operative.

Le sei classi previste sono:

- `air leak`
- `air leak engine inside cabin`
- `background noise`
- `idling`
- `normal engine inside cabin`
- `oil cap off engine inside cabin`

---

##  Modelli Sviluppati

Sono stati confrontati tre modelli principali:

| Modello | Descrizione |
|--------|-------------|
| **HybridCNNImproved** | CNN 2D su mel-spettrogrammi, con dati segmentati |
| **CNN + Reverse & Segmentazione** | CNN 2D su mel-spettrogrammi con reverse audio e segmentazione |
| **ResNetHybrid** | Architettura duale che integra spettrogrammi e feature numeriche dal segnale audio |

---

##  Setup Sperimentale

- **Ambiente**: Google Colab
- **Librerie principali**: `PyTorch`, `Librosa`, `Matplotlib`, `Scikit-learn`
- **Modello migliore**: `HybridCNNImproved`, con F1-score medio pari a **0.85**

---

##  Risultati Principali

| Modello | Precision | Recall | F1-score |
|---------|-----------|--------|----------|
| HybridCNNImproved | 0.87 | 0.84 | 0.85 |
| CNN + Reverse & Segmentazione | 0.89 | 0.85 | 0.86 |
| ResNetHybrid | 0.86 | 0.82 | 0.83 |

 L’approccio con segmentazione dei segnali ha permesso un significativo incremento della performance grazie all’aumento del numero di campioni.

---

## Metriche & Visualizzazioni

- Curve di apprendimento (loss/accuracy per epoca)
- Confusion Matrix per ogni modello
- Metriche macro: *accuracy, precision, recall, F1-score*

---

## Requisiti

- Python ≥ 3.8  
- PyTorch ≥ 1.13  
- Librosa  
- Matplotlib  
- Scikit-learn  
- Numpy  

Installa i requisiti con:

```bash
pip install -r requirements.txt
```

---

## Come Eseguire

1. Clona il repository:
   ```bash
   git clone https://github.com/tuo-username/car-echo-fix.git
   cd car-echo-fix
   ```

2. Carica i file audio del dataset in `./data/`

3. Esegui il training:
   ```bash
   python train_hybridcnn.py
   ```

4. Visualizza i risultati:
   ```bash
   python evaluate.py
   ```

---

## Possibili Estensioni

- Introduzione di tecniche di regularizzazione (Dropout, BatchNorm)
- Ampliamento del dataset con suoni reali in ambienti rumorosi
- Compressione del modello per uso su dispositivi embedded (pruning, quantizzazione)

---

## License

MIT License – vedi `LICENSE` per dettagli.

---

## Autori

Bishoy Zakhary – Ingegnere Informatico, AI & ML
Tocu Gheorghita Razvan – Ingegnere Informatico, AI & ML
Progetto universitario, 2025
