# 📊 Analyse Statistique – Résultats de Thèse

*Ce dépôt présente les analyses statistiques du chapitre de résultats de la thèse de doctorat en Microbiologie.*

---

## 🎓 Contexte Académique
**THÈSE DE DOCTORAT (LMD 3ᵉ Cycle)**  
**Spécialité :** Microbiologie Appliquée  
**Titre :** *Recherche d'antibiotiques d'origine actinobactérienne actifs contre les bactéries impliquées dans les infections communautaires*  
**Candidate :** BENMOUMOU Sarra  
**Institution :** Université  de Blida 1
**Année :** 2025  

---

## 🎯 Objectifs Scientifiques

Cette analyse vise à caractériser les relations entre paramètres cliniques et microbiologiques à partir d'isolats bactériens, avec pour finalités :

1. **Étude des associations clinico-microbiologiques :**
   - Espèce bactérienne × Genre des patients
   - Espèce bactérienne × Catégorie d'âge
   - Résistance antibiotique × Paramètres démographiques

2. **Évaluation des profils de multi-résistance :**
   - Prévalence selon les espèces bactériennes
   - Distribution par classe d'antibiotiques
   - Corrélations avec les facteurs cliniques

---

## 📈 Méthodologie Statistique

### 🔍 Exploration des Données
- Nettoyage des jeux de données (valeurs manquantes, cohérence)
- Catégorisation des variables :
  - **Âge :** 5 classes (Nouveau-né <1an, Enfant 1-12ans, Adolescent 13-18ans, Adulte 19-65ans, Senior >65ans)
  - **Résistance :** Sensible/Intermediaire/Résistant selon EUCAST

### 📊 Approche Analytique
| Type de Données | Test Statistique | Visualisation |
|----------------|------------------|---------------|
| Variables catégorielles | Test du χ² (Chi²) | Diagrammes en barres empilées |
| Petits effectifs (n<5) | Test exact de Fisher | Mosaic plots |
| Variables ordinales | Kruskal-Wallis | Boxplots/Violin plots |
| Comparaisons multiples | Correction de Bonferroni | Heatmaps |

## 🛠️ Outils Computationnels
```python
# Exemple de pipeline d'analyse
import pandas as pd
from scipy.stats import chi2_contingency

def analyse_resistance(df):
    tableau_contingence = pd.crosstab(df['Espèce'], df['Résistance'])
    chi2, pval, _, _ = chi2_contingency(tableau_contingence)
    return pval
```
### 💻 Installation de l'Environnement
Option 1 : Jupyter Notebook

    Installer Anaconda (recommandé)

    Créer l'environnement :

```bash
Copy

conda create -n analyse_these python=3.9
conda activate analyse_these
pip install -r requirements.txt
jupyter notebook
```
Option 2 : Visual Studio Code

    Installer VSCode

    Ajouter les extensions :

        Jupyter (Microsoft)

        Python (Microsoft)

    Configurer l'interpréteur Python 3.9+

### 📦 Dépendances (requirements.txt)
Copy

```
pandas>=1.4.0
matplotlib>=3.5.0
seaborn>=0.11.2
scipy>=1.8.0
statsmodels>=0.13.2
jupyterlab>=3.4.0
```

## ▶️ Guide d'Utilisation

    Structure des Données :

        Placer les fichiers bruts dans /data

        Format requis : CSV avec encodage UTF-8

    Exécution des Analyses :
    bash
    Copy

    cd notebooks/
    jupyter notebook analyse_principale.ipynb

    Sorties :

        Figures : /results/figures/*.png (300 dpi)

        Tables : /results/tables/*.csv

        Rapports : /results/reports/analyse_[date].html




