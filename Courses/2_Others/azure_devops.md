# Devops

## What is devops ?
Fludifier les échanges et les process pour qu'il n'y ait pas de résistance d'autres corps de métier. Être agile. Réussir à aligner tout le monde sur les mêmes objectifs.

**Points importants :**
- Augmenter la fréquence de déploiement
- Conserver un objectif de vélocité tout en cherchant la sécurité.
- *Travailler sur des équipes de petites tailles pour éviter les conflits*
- Outillage : *La bonne gestion des outils* (essayer d'automatiser au maximum). 
- 

**Priorisation** : humain (organisation des équipes) **>** process (gestion des outils).

### Schéma :
<img src="resources/devops scheme.PNG" alt="devops scheme" />

- **Feedback** : être factuel, permettre aux équipes d'améliorer les processus. Donner des résultats aux clients. Comprendre si on atteint les objectifs et chercher à améliore grâce à cela.

## Pourquoi faire du devops ?
- **Augmenter son bénéfice** (génération de valeur pour le client)

###  **Optimiser les coûts** / valeurs. 
Réduire les tâches ingrates. Tester, deployer, faire des maj, de la maintenance : tout cela coûte. Les processus interviennent à ce niveau pour optimiser et automatiser.

Principe d'**intégration continue**. S'appuyer sur des automates pour réaliser les tests, maintenances, maj, etc.

Principe de **déployement continu**. S'organiser, matérialiser, visualiser.

Un **Pipeline** est la description de toutes les actions nécessaires pour arriver à l'*intégration?*.

**Version control** : Généralement basé sur un git. Avoir un système de version permet d'être efficace rapidement notamment pour délivrer des features stables sans compromettre le code principal. <br />
Git flow n'est plus la solution actuelle. Maintenant on cherche la simplicité au maximum. Basé sur une branche main et directement des branches features. Le **trunk-based development** ?