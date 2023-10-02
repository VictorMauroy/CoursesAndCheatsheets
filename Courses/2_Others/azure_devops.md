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

- **Optimiser les coûts** / valeurs. 
Réduire les tâches ingrates. Tester, deployer, faire des maj, de la maintenance : tout cela coûte. Les processus interviennent à ce niveau pour optimiser et automatiser.

## Principes fondamentaux

Principe d'**intégration continue**. S'appuyer sur des automates pour réaliser les tests, maintenances, maj, etc.

Principe de **déployement continu**. S'organiser, matérialiser, visualiser.

Un **Pipeline** est la description de toutes les actions nécessaires pour arriver à l'*intégration?*.

**Version control** : Généralement basé sur un git. Avoir un système de version permet d'être efficace rapidement notamment pour délivrer des features stables sans compromettre le code principal. <br />
**Git flow** n'est pas la meilleure solution pour du devops (peu adapté à du déployement court et agile). Maintenant on cherche la simplicité au maximum. Basé sur une branche main et directement des branches features. 
Le [**trunk-based development**](https://trunkbaseddevelopment.com/) est la meilleure solution actuelle.

**Infrastructure as Code (IaC)** : Gérer les ressources à travers du code. Partage simplifié des informations. Répéter des déployements de ressources sans risque de valeurs mal positionnés. Pouvoir faire des debug.

**Microservices** : À l'inverse de l'architecture monolithique/layered, la structure microservice éclate et sort tous les composants de l'applicatif dans des instances autonomes et spécialisées. Utilisation de conteneur. Eviter des processus longs et complexes à intégrer de la structue monolitique. Augmente le nombre d'objets à monitorer donc les problèmes peuvent se révéler plus complexes à identifier.

**Containers** : Utilisation de containers, permet de mettre en place l'infrastructure microservices. Améliorer la qualité finale. Consomme peu de ressources comparé aux machines virtuelles. <br />
**Kubernetes :** l'un des orchestrateurs les plus utilisés; Il offre le pus grand nombre de services.




## Différence structure horizontale et verticale
<img src="resources/devops structure.PNG" alt="devops structure" />




## Composition Azure Devops
<img src="resources/devops composition.PNG" alt="devops composition img" />