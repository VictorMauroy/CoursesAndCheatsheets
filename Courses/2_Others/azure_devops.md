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




## Pipeline et intégration continue

<img src="resources/azure pipeline.PNG" alt="azure pipeline img" />

L'intégration ce sont les tâches qui permettent de préparer des artéfacts à la release.

### La pipeline classique
La pipeline classique aussi nommée Visual Designer Pipeline. Elle n'est plus à utiliser.
<img src="resources/visual designer pipeline.PNG" alt="classic pipeline img" />

### La YAML pipeline
Réalisé avec un assistant capable de générer du code.
<img src="resources/YAML pipeline.PNG" alt="yaml pipeline img" />

## Deployment patterns

### Blue green deployment
Blue green deployment is an application release model that gradually transfers user traffic from a previous version of an app or microservice to a nearly identical new release—both of which are running in production. (Redhat)
<img src="resources/blue green.PNG" alt="blue green img" />

### Others deployment patterns
- **Canary releases** : Le canary release est un pattern qui permet de faire tester les dernières modifications réalisées (appelée version N+1) à une tranche de population restreinte avant de réaliser un déploiement général de cette version. (MyAgilePattern)

- **A/B testing** : Faire coexister plusieurs versions d'une même feature. Permet de comparer deux versions avec des metrics afin d'établir des différences et des valeurs ajoutées.

- **Dark launching** : Déployer de manière masquée/cachée une fonctionnalité. 

<br />

**Schéma de déploiement classique :** <br />
Dev => test => staging => production

Les **Feature toggles** sont des changements apportés à une application où vont coexister la nouvelle version d'une feature et une ancienne. La feature toggle représente cette nouvelle version de la feature. L'ancienne version reste un certain temps jusqu'à ce que l'utilisateur se soit adapté à la nouvelle.
<img src="resources/feature toggle.PNG" alt="feature toggle img" />

