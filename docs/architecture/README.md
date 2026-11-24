# dat-gabarit 2.0

Gabarit du document d'architecture technique (DAT) du portail Nexus360 - mission fil rouge D01,
module Architecture Hexagonale & DDD, Bachelor 3. Toutes les consignes sont dans le sujet
(Projet_01_Sujet) ; la méthode, étape par étape, dans le livret Projet_05_Livret_Fil_Rouge.

## Utilisation

1. Copiez le contenu de ce dossier dans le dépôt de votre équipe, sous `docs/architecture/`.
2. Déposez les photos du mur d'event storming et de la context map dans `annexes/`.
3. Remplissez `DAT.md` section par section (sections 0 à 12). Une décision importante = un fichier
   `adr/ADR-00x.md` ; au moins deux, dont `ADR-002` sur la réutilisation entre contextes.
4. Diagrammes : fichiers `.puml` dans `diagrammes/` (un `composants` par contexte cœur, une séquence
   au moins). Installez l'extension VS Code **PlantUML** (jebbs) ; aperçu avec `Alt+D` (Windows/Linux)
   ou `Option+D` (macOS).
5. Export PNG pour que GitHub affiche les images dans `DAT.md` : palette de commandes,
   « PlantUML: Export Current Diagram », format PNG, dans le même dossier `diagrammes/`.
6. Chaque membre commite lui-même ses sections : la section 12 est vérifiée avec `git log`.
