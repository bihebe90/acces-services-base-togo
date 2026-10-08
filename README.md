# Accès des ménages aux services de base au Togo

Analyse de l'accès des ménages à l'eau, à l'assainissement, à l'énergie de cuisson et à l'éclairage, à partir d'une enquête ménages (6 749 ménages, 5 régions), selon les normes de suivi des ODD (JMP OMS/UNICEF pour l'eau et l'assainissement, ODD 7 pour l'énergie).

**Auteur :** Bihèbè KAGNIRA, statisticien : bihebekagnira@gmail.com

**Consulter les résultats sans installer Python :** ouvrir [`rapport/acces_service_base.html`](rapport/acces_service_base.html) (à télécharger puis ouvrir dans un navigateur), ou lire directement le notebook dans `notebooks/`.

## Contenu de l'analyse

1. Construction d'indicateurs binaires par service, avec contrôle automatique du classement des modalités.
2. Taux d'accès avec intervalles de confiance et analyse de sensibilité sur les modalités ambiguës.
3. Indice synthétique d'accès (0 à 1) et classement des ménages (faible, moyen, bon).
4. Disparités régionales : tableaux, test du khi-deux, graphiques et cartes.
5. Régression logistique (rapports de cotes) et validation croisée.

## Structure du dépôt

```
.
├── notebooks/
│   └── acces_service_base.ipynb
├── donnees/
│   ├── donneesbrutes/        # BASE_SAN.sav (non diffusé)
│   └── donneescrees/         # tableaux exportés par le notebook
├── shapes/
│   └── gadm41_TGO_1.json     # limites des régions (GADM 4.1, non diffusé)
├── outputs/
│   └── figures/              # graphiques et cartes générés
├── rapport/
│   └── acces_service_base.html  # rapport complet, sans le code
├── requirements.txt
└── README.md
```

## Reproduire l'analyse

```bash
pip install -r requirements.txt
cd notebooks
jupyter notebook acces_service_base.ipynb
```

Le notebook doit être lancé depuis le dossier `notebooks/`. Les chemins sont relatifs à la racine du projet.

## Données

- **Enquête :** `BASE_SAN.sav`. Les microdonnées ne sont pas diffusées dans ce dépôt. Pour reproduire l'analyse, placez le fichier dans `donnees/donneesbrutes/`.
- **Limites administratives :** GADM 4.1, niveau 1 (régions). La licence GADM n'autorise pas la redistribution : téléchargez le fichier `gadm41_TGO_1.json` sur https://gadm.org et placez-le dans `shapes/`.

## Limites

Les résultats sont non pondérés et décrivent l'échantillon : ils ne constituent pas des estimations nationales. Les autres limites sont détaillées à la fin du notebook.
