# Regarder, voir, donner à voir
**Épistémologie du regard : de l'histoire de l'art à la vision par ordinateur**

## À propos
Ce dépôt GitHub regroupe l'ensemble du code, des données, des résultats d'expérimentations et des documents annexes réalisés dans le cadre de mon mémoire de master « Technologies numériques appliquées à l'histoire » École nationale des chartes - PSL, 2026.

Il documente les travaux pratiques menés lors de mon stage au **musée d'Orsay** au Service des données patrimoniales numériques, sous la supervison de Benoit Deshayes (EPMO) et Marion Charpier (TORNE-H ENC) dans le cadre du projet de recherche **TORNE-H**. L'expérimentation porte principalement sur le **fonds photographique Éric Jantzen** et interroge la manière dont l'introduction de la vision par ordinateur reconfigure les opérations de classement, de description et de mise en visibilité des images patrimoniales.

---

## Arborescence

```text
Regarder-voir-donner-a-voir/
├── README.md
├── benchmarks_cv/
│   ├── data/
│   ├── florence/
│   │   ├── notebook_florence.ipynb
│   │   └── resultats/
│   │       ├── abbeville_14/
│   │       ├── abbeville_16/
│   │       └── celestin_4b/
│   ├── llava/
│   │   ├── notebook_llava.ipynb
│   │   └── resultats/
│   │       ├── abbeville_14/
│   │       ├── abbeville_16/
│   │       └── celestin_4b/
│   └── molmo/
│       ├── notebook_molmo.ipynb
│       └── resultats/
│           ├── abbeville_14/
│           ├── abbeville_16/
│           └── celestin_4b/
├── donnees_jantzen/
│   ├── batiments.json
│   ├── modele
│   ├── personne.json
│   ├── photo.json
│   └── thesaurus.json
├── fonds_jantzen/
│   └── fiche_inventaire_jantzen.pdf
├── notebook_sam3/
│   ├── data/
│   ├── notebook_sam3_modifie.ipynb
│   └── resultats/
│       ├── vis/
│       ├── vis.angl/
│       └── vis.fr/
└── tiamat_frontend/
    └── .gitkeep

```
## Contenu détaillé

### 1. `benchmarks_cv/` (Computer Vision)

Ce dossier documente l'écart entre le regard algorithmique et le regard expert. Il contient les benchmarks de trois modèles 
  - Florence-2
  - LLaVA avec Grounding DINO
  - Molmo
testés sur un corpus de façades et détails architecturaux.

* L'objectif est d'évaluer la **topologie perceptive** de ces modèles face à une ontologie documentaire stricte 

### 2. `donnees_jantzen/`

Ce dossier contient la modélisation ainsi que les données du fonds Eric Jantzen, destinée à alimenter la cartographie interactive du projet.
Le travail de traitement et de modélisation du fonds a été réalisé en collaboration et sous la supervision de Benoit Deshayes.

* Les données (JSON) ont été structurées autour de **l'immeuble** comme entité-pivot, dépassant les métadonnées IPTC hétérogènes d'origine.
* Le `thesaurus.json` reflète les choix de granularité opérés pour ce corpus (par exemple, le choix des matériaux et ouvertures pertinents pour l'architecture parisienne).

### 3. `fonds_jantzen/`

* **`fiche_inventaire_jantzen.pdf`** : Fiche d'inventaire du fonds Éric Jantzen respectant la norme de description archivistique **ISAD(G)**. Elle constitue le socle institutionnel et documentaire sur lequel s'appuie l'expérimentation numérique.

### 4. `notebook_sam3/`

Première expérimentation d'extraction et de segmentation fine des éléments architecturaux.

* **`notebook_sam3_modifie.ipynb`** : Basé sur le travail initial de Marion Charpier, ce script documente la chaîne de traitement (Grounding DINO + Segment Anything + CLIP) tente de résoudre des problématiques de granularité visuelle.

### 5. `tiamat_frontend/`

*Dossier accueillant le code source de l'interface utilisateur.*
TiamaT est l'outil d'annotation déployé dans le projet TORNE-H par Marion Charpier. Le front-end a été conçu pour permettre un cycle itératif de correction humaine des prédictions algorithmiques, assumant que l'annotation experte patrimoniale n'est jamais figée.

---

## Utilisation et Reproductibilité

* Les scripts d'extraction et les benchmarks sont fournis sous forme de carnets Jupyter (`.ipynb`).
* Leur exécution requiert un environnement Python adapté et, pour les modèles LLaVA et Molmo, un accès à une puissance de calcul GPU.
* *Note : Les jeux de données complets (images hautes résolutions) ne sont pas tous inclus dans ce dépôt pour des raisons de droits et de poids, mais les échantillons de test (`data/`) permettent de reproduire les benchmarks.*

## Équipe et Contributions

* **Eva Rivière** : Autrice du mémoire, développement Front-End (TiamaT), exécution des benchmarks CV, modification des pipelines SAM 3, conception de l'inventaire ISAD(G) et co-traitement des données.
* **Marion Charpier** : Direction du mémoire, conception du notebook SAM 3 originel et supervision de l'ontologie d'annotation.
* **Benoît Deshayes** : Encadrement stage, Co-traitement et structuration des données JSON (fonds Jantzen).
* **Projet TORNE-H** : Cadre de recherche institutionnel réunissant le musée d'Orsay, le musée des Arts décoratifs, la BnF et l'École nationale des chartes.

```

```
