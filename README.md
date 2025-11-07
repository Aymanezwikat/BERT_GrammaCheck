New-Item -Path . -Name "README.md" -ItemType "file" -Force
@"
# 🧠 BERT_GrammaCheck

**BERT_GrammaCheck** est une application basée sur le modèle **BERT** qui permet de **vérifier la grammaticalité de phrases en anglais**.  
Ce projet comprend deux grandes parties :
1. Le **fine-tuning du modèle BERT** sur le jeu de données **CoLA (Corpus of Linguistic Acceptability)**.
2. Une **application Streamlit** pour tester le modèle fine-tuné de manière interactive.

---

## 🚀 Objectif du projet

L’objectif de ce projet est de démontrer l’utilisation du **fine-tuning** d’un modèle de langage pré-entraîné (BERT) pour une tâche de **classification binaire** :  
> Déterminer si une phrase en anglais est grammaticalement correcte ou incorrecte.

---

## 🧩 Architecture du projet

Voici la structure détaillée du dossier :

\`\`\`
📦 BERT_GrammaCheck/
│
├── 📁 model_save/                # Modèle BERT fine-tuné et tokenizer sauvegardés
│   ├── config.json
│   ├── model.safetensors
│   ├── special_tokens_map.json
│   ├── tokenizer_config.json
│   └── vocab.txt
│
├── 📁 notebook_model/
│   └── bert_cola_fine_tuning.ipynb   # Notebook de fine-tuning du modèle BERT
│
├── 📁 venv/                    # Environnement virtuel (non suivi par Git)
│
├── 📄 app.py                   # Application Streamlit pour tester le modèle
├── 📄 requirements.txt         # Dépendances Python nécessaires
├── 📄 .gitignore               # Fichiers et dossiers à ignorer par Git
└── 📄 README.md                # Description complète du projet
\`\`\`

---

## 🧠 Partie 1 — Fine-tuning du modèle BERT

Le notebook `bert_cola_fine_tuning.ipynb` contient :
- Le **chargement du dataset CoLA**
- La **préparation des données**
- L’**entraînement (fine-tuning)** du modèle
- La **sauvegarde du modèle** dans `model_save/`

Le modèle final classe une phrase :
- ✅ correcte grammaticalement
- ❌ incorrecte grammaticalement

---

## 💻 Partie 2 — Application Streamlit

`app.py` permet de tester le modèle via une interface web.

### Lancer l’application :
\`\`\`bash
streamlit run app.py
\`\`\`

---

## 🧰 Installation

\`\`\`bash
git clone https://github.com/ton-nom-utilisateur/BERT_GrammaCheck.git
cd BERT_GrammaCheck
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
streamlit run app.py
\`\`\`

---

## 🧑‍💻 Auteur
Projet réalisé par **[Ton Nom]** — 2025  
Fine-tuning du modèle **BERT** pour la correction grammaticale anglaise.
"@ | Out-File -FilePath README.md -Encoding UTF8
