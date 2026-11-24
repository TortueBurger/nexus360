# Nexus360 - Document d'architecture technique (DAT)

Projet final du module **Architecture Hexagonale & DDD** (Bachelor 3 Informatique - Développement, Ynov Val d'Europe, 2026-2027). Référence : AHD-B3-PROJET, mission D01 « Concevoir l'architecture logicielle cible ».

**Auteur :** Elias PARCET (travail seul).

## Le projet
Nexus360 est une ESN de 480 collaborateurs qui vend à des entreprises clientes le travail de ses consultants et de ses sous-traitants. Son portail métier gère tout le cycle d'une mission : demande du client, proposition de consultants, affectation, saisie et validation du CRA mensuel, facture, paiement du sous-traitant. Il remplace l'application historique GesMiss.

Cette première partie du dépôt est **le DAT** : la conception de l'architecture logicielle cible, avant tout développement. Elle ne contient pas de code applicatif.

## Ce que décrit le DAT
- **Le métier :** glossaire (langage ubiquitaire), hypothèses sur ce que l'énoncé ne tranche pas.
- **La découpe :** six bounded contexts. Le **Staffing** est le sous-domaine cœur ; Suivi d'activité et Facturation sont des supports ; Notifications, Signature électronique et Identité et accès sont génériques. Une context map nomme chaque relation (ACL, conformiste, client-fournisseur).
- **Le modèle du cœur :** deux aggregates, `PlanningConsultant` (garde la charge à 100 % maximum et les règles d'affectation) et `DemandeClient`, avec leurs invariants, leurs domain events, leurs politiques et leurs repositories.
- **L'architecture hexagonale du Staffing :** ports primaires et secondaires, adapters (dont des adapters en mémoire pour les tests), arborescence cible d'un monolithe modulaire et règle des dépendances.
- **Un scénario :** la séquence « affecter un consultant à une mission », avec le cas de refus.
- **Les décisions :** deux ADR (cohérence entre aggregates, réutilisation entre contextes), SOLID appliqué à l'architecture, limites et risques.

## Contenu du dépôt
```
docs/architecture/
├── DAT.md                          le document (sections 0 à 12)
├── diagrammes/
│   ├── context-map.puml / .png          carte des contextes
│   ├── composants-staffing.puml / .png  hexagone du contexte Staffing
│   └── sequence-01.puml / .png          séquence d'affectation
├── adr/
│   ├── ADR-001.md                  PlanningConsultant garde la charge (R1)
│   └── ADR-002.md                  réutilisation entre contextes
└── annexes/                        pièces annexes (event storming)
Questions_TP.md                     exercices du livret, avec les réponses
```

## Lire le DAT
Commencer par [`docs/architecture/DAT.md`](docs/architecture/DAT.md). Les diagrammes y sont intégrés ; les sources PlantUML (`.puml`) sont dans `docs/architecture/diagrammes/`.

## Modifier les diagrammes
Installer l'extension VS Code **PlantUML** (`jebbs.plantuml`). Aperçu : `Alt+D`. Export : palette de commandes, « PlantUML: Export Current Diagram », format PNG, dans le même dossier `diagrammes/`.

## Gabarit
Le DAT suit le gabarit **dat-gabarit 2.0** fourni par l'enseignant.
