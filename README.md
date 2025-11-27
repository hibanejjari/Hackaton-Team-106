
#  Hackaton-Team-106
### Solution de suivi & versionnage des normes avec analyse d’impact PLM
## 📚 Sommaire

- [🎯 Objectif du projet](#-objectif-du-projet)
- [📂 Structure du dépôt](#-structure-du-dépôt)
- [🔧 Pipeline technique](#-pipeline-technique)
- [📊 Diagramme dimpact-traceabilité](#-diagramme-dimpact-traceabilité)
- [✔️ Fonctionnalités du prototype](#️-fonctionnalités-du-prototype)
- [🖥️ Maquette de linterface-utilisateur-ui](#️-maquette-de-linterface-utilisateur-ui)
- [📅 Roadmap--to-do-list](#-roadmap--to-do-list)
- [👥 Équipe](#-équipe)
- [📜 Licence](#-licence)

---

##  Objectif du projet

Développer un prototype permettant :

- de versionner les normes (V1, V2, V3…)
- de comparer automatiquement chaque nouvelle version à la précédente
- d’en extraire les changements chiffrés (Δ seuils, Δ limites…)
- de transformer ces changements en exigences produit
- d’identifier les pièces/ensembles impactés via un dataset PLM
- de produire un diagramme d’impact clair
- d’évaluer la conformité du système

**Résumé :** Une chaîne complète *“Norme → Δ → Exigence → Pièces PLM → Impact → Conformité”*.

---

##  Structure du dépôt

```
Hackaton-Team-106/
│
├── README.md
├── data/
│   ├── norme_v1.pdf
│   ├── norme_v2.pdf
│   ├── plm_dataset.csv
│   └── requirements.json
│
├── src/
│   ├── extract_norm.py
│   ├── compare_versions.py
│   ├── generate_requirements.py
│   ├── map_to_plm.py
│   └── impact_analysis.py
│
└── ui/
    └── mockup_interface.png
```

---

## 🔧 Pipeline technique

```
     ┌──────────────┐      ┌──────────────┐
     │ Norme V1.pdf │      │ Norme V2.pdf │
     └───────┬──────┘      └──────┬───────┘
             │                    │
             ▼                    ▼
     Extraction & parsing des exigences
             │
             └──────────► Comparaison (Diff)
                           Δ valeurs, Δ seuils…
                                 │
                                 ▼
                  Génération de nouvelles exigences
                                 │
                                 ▼
                       Mapping vers pièces PLM
                                 │
                                 ▼
                     Analyse d’impact (coût, délai,
                            masse, CAO, criticité)
                                 │
                                 ▼
                       Résultat de conformité
```

---

## 📊 Diagramme d’impact (traceabilité)

```
📘 Nouvelle Norme (V2)
          │ Δ
          ▼
🧩 Exigence Produit
"Résistance thermique ≥ 1300°C"
          │
          ▼
🔧 Pièces PLM impactées
- D142 Moteur
- D088 Fuselage Centrale
- D234 Boîtier Électronique
          │
          ▼
📉 Impacts
- Coût : +2.5M €
- Masse : +15 kg
- Temps CAO : 1014 h
- Délai fournisseur : +45 jours
          │
          ▼
⚠️ Conformité : NON conforme
```

---

## ✔️ Fonctionnalités du prototype

### Versionnage des normes
- Import des formats PDF
- Conversion en JSON structuré
- Historique des versions

### Détection automatique des changements
- Δ seuils
- Δ limites physiques
- Δ conditions de test
- Ajouts / suppressions d’articles

### Génération d’exigences ingénierie
- Format clair
- Valeur cible
- Unité
- ID unique

### Mapping vers les pièces PLM
- Identification des éléments impactés
- Pondération selon criticité

### Analyse d’impact multi-critères
- Coût
- Masse
- Temps CAO
- Délai d’approvisionnement
- Risque fournisseur

### Évaluation de la conformité
- Conforme / Non conforme
- Niveau de sévérité
- Liste des actions requises

---

## 🖥️ Maquette de l’interface utilisateur (UI)

```
┌───────────────────────────────────────────┐
│    🛠️  Comparateur de Normes (Prototype)  │
├───────────────────────────────────────────┤
│  V1 : [Importer]     V2 : [Importer]      │
│                                           │
│         [Comparer les versions]           │
├───────────────────────────────────────────┤
│            Résultats de la comparaison    │
│   ─────────────────────────────────────── │
│   Exigence      Avant      Après     Δ    │
│   --------------------------------------- │
│   Température   1200°C     1300°C   +100  │
│   Vibrations      4G         5G     +1G   │
│                                           │
├───────────────────────────────────────────┤
│           Pièces PLM impactées            │
│   - D142 Moteur (Critique)                │
│   - D088 Fuselage Centrale                │
│   - D234 Boîtier Électronique             │
│                                           │
│  ⚠️ Conformité globale : NON CONFORME     │
└───────────────────────────────────────────┘
```

---

## 📅 Roadmap / To-Do List

### Phase 1 — Analyse
- [x] Sélection de la norme V1/V2
- [x] Analyse du dataset PLM
- [x] Définition du modèle d’exigence

### Phase 2 — Technique
- [ ] Extraction PDF
- [ ] Diff automatique V2-V1
- [ ] Génération des exigences
- [ ] Mapping PLM
- [ ] Analyse d’impact

### Phase 3 — Interface
- [ ] Maquette UI
- [ ] Prototype Streamlit

### Phase 4 — Finalisation
- [ ] Diagramme d’impact
- [ ] Slide Deck Jury
- [ ] Démonstration finale

---

## 👥 Équipe

| Nom | Rôle |
|------|------|
| … | Analyse normative |
| … | Implémentation technique |
| … | PLM / Impact |
| … | Visualisation / Slides |

---

## 📜 Licence

Projet réalisé dans le cadre du **Hackaton Ingénierie & PLM — Team 106**.


┌─────────────────────────────────────────────────────────────┐
│ 🔎 Portail des Normes Automobiles (Source globale)           │
├─────────────────────────────────────────────────────────────┤
│ Recherche : [ ISO / UNECE / R100 / sécurité / batterie ]     │
│ Filtre : [ 🇪🇺 UE ] [ 🇺🇳 ONU ] [ 🇺🇸 USA ] [ ⚙️ ISO ] [ 🔌 Électrique ] │
├─────────────────────────────────────────────────────────────┤
│ 📘 ISO 26262   • Sécurité fonctionnelle                     │
│     Versions : 2011 | 2018 | 2022                           │
│     Source : iso.org                                        │
│     [Voir] [Comparer versions] [Importer]                   │
├─────────────────────────────────────────────────────────────┤
│ 📘 UNECE R100 • Batteries véhicules électriques              │
│     Versions : Rev.3 (2019) | Rev.4 (2023)                  │
│     Source : unece.org                                      │
│     [Voir] [Comparer versions] [Importer]                   │
├─────────────────────────────────────────────────────────────┤
│ 📘 FMVSS 305 • Electrical Safety (USA)                       │
│     Versions : 2015 | 2018 | 2022                           │
│     Source : nhtsa.gov                                      │
│     [Voir] [Comparer]                                       │
└─────────────────────────────────────────────────────────────┘

