# <span style="color: green"><u>**Office/Microsoft 365 - Power Platform**</u></span>

## **Licence**
Afin de travailler en tant que développeur sur office 365, il faut le droit d’acheter sur le compte (rang admin). La licence par défaut étant une license famille pour le grand public.

Il y a de nombreuses autres licences à acheter, elles ne comprennent pas toutes les applications. <br>
*Centre d’administration ⇒ Facturation ⇒ Acheter des services.*

Dans **Utilisateurs**, nous pouvons gérer les différentes personnes capables d’utiliser notre compte : cela permet notamment d’**assigner des licences** et permettent à ces personnes d’accéder uniquement aux applications dont elles ont besoin.

**Microsoft 365** = Office 365 + licences Windows (Word, Excel, etc.) <br>
**Office 365** = Suite d’application à destination des utilisateurs finaux
Azure plutôt orienté administrateurs et IT pro.


## **Introduction à Power Platform**
Afin d’utiliser Power Platform, il faut acheter une licence spéciale et l’attribuer à nos utilisateurs. *(Centre d’admin ⇒ Facturation ⇒ Acheter des services ⇒ Power Platform)*

[Power Platform admin center](https://aka.ms/ppac)

**Power Platform est un pack de produits** contenant les produits nécessaires à développer, distribués sous la plateforme Office 365 par Microsoft. L’offre bénéficie d’une période d’essai / de licences d’essai. **Il permet du développement Low Code voire No Code.**

### Les cinq produits Power Platform

**Power Apps :**
- Développer des applications
- Réaliser des canvas (tablette, mobile ou teams)
- Créer des Model Driven (Data driven)

**Power Automate :** <br>
*(Automatisation à partir de flux pour répondre à des événements en déclenchant une série d’action)*
- Workflow
- Cloud Flow *(Ex: créer une fonction automatique pour notifier par SMS lorsque nous recevons un email)*
C’est toujours un trigger suivi d’une ou plusieurs actions derrière (qui s’exécutent en réponse à ce trigger.)
    * Flux manuel / flux bouton
    * Flux planifiés
    * Flux automatisés
- Business Process Flow
- RPA Flow *(Travailler avec des applications héritées, de vieilles applications)*

**Power BI :** <br>
Data Viz(Visualization) & Data Prep(Preparation)

**Power Virtual Agent :**
<br>Créer des Chat Bots

**Power Pages :**
<br> Créer des sites web grand public


## **Les environnements**
**Utilité :** Séparer la production du développement afin d’avoir des sources de données et des applications différentes (notamment si les apps ne sont pas testées ou validées).

**Les solutions** permettent de transporter les développements d’un environnement à un autre.

Par défaut, nous travaillons dans l’environnement Production.
Lorsque nous développons une application, il vaut mieux travailler avec différents environnements, notamment un environnement “de développement” puis passer à celui de production.

Pour **créer un nouvel environnement** : Aller au Power Platform admin center puis sur Environnements ⇒ New.

L’**environnement Developer** est réservé à un unique développeur et personne ne peut y être invité. <br>
**Production** est collaboratif, il est possible d’en créer plusieurs afin d’avoir de donner l’accès à différents groupes de personnes. <br>
**Sandbox** est un environnement qu’il est possible de copier ou réinitialiser.

**Note :** Il est préférable de toujours créer des objets dans une solution plutôt que dans un environnement. Cela permet notamment de définir correctement le publisher.



## **Créer une application**
1) Afin de créer une application, **commencez par passer en environnement développeur**. 

2) **Créez une solution** (un conteneur d’objets/d’applications) et **ajoutez un publisher** (concepteur de l’app; indique quelle entité est à l’origine de la publication du contenu : un dev ou une entreprise)

3) Une fois la solution créée, nous pouvons commencer à **créer des tables** (en restant dans la solution) si nous avons besoin d’une BDD. Il est possible d’utiliser des data models pour démarrer rapidement.

**Formulaire (form office365) :** Permet de visualiser voire d’interagir avec un enregistrement unique d’une table.

**Vue (view office365) :** Permet de visualiser, sur une même page, plusieurs enregistrements qui sont présents sur une même table.

**Business rule :** permet d’ajouter des contraintes / des règles de gestion. Contraintes qui vont être validées avant qu’une donnée ne soit enregistrée dans la bdd.

**Business process :** Réaliser des workflows; Mettre en place des processus que l’entreprise devra suivre.

**SendGrid :** Service permettant d’associer des boîtes mails et pouvant envoyer des mails ou SMS lorsqu’il est appelé (notamment par des flows (Business flow) de Power Automate).

Globalement, **nous utilisons Power Automate lorsque nous avons besoin d’automatiser des actions.**
Lors de la définition d’un flow, il est possible de relier des nodes et ainsi d’appeler de nombreux services. Notamment le Business Process où nous avons chercher des données dans la BDD du Dataverse puis avons envoyé un mail ou une requête sur Teams afin d’attendre une réponse acceptée ou refusée.

### Dataverse
**Le dataverse est une base de données associée à un environnement particulier.**

Les **Data Models** sont des modèles que nous pouvons utiliser afin de commencer avec une base de tables lorsque nous créons une base de données. En se basant sur des modèles fréquemment utilisés.

Dans le dataverse, il est possible de créer nos propres tables, de renseigner de nombreux paramètres personnalisés (y compris les relations et les propriétés des champs/colonnes). Il est ensuite possible de rapidement créer des formulaires et des vues grâce au Dataverse.

## **PowerBI**
**PowerBI étant essentiellement utilisé pour écrire et lire des rapports.** Il est possible d’utiliser une licence gratuite mais nous sommes restreint à notre propre travail et il est impossible de partager nos rapports ou lire ceux d’autres personnes.

Ces rapports peuvent notamment inclure **de nombreux types de graphiques**.

N’est pas un outil mais plutôt une suite d'outils. **Les principaux outils** sont : 
- **PowerBI Desktop** (Conception de rapports)	
- **PowerBI Service** (Héberger les rapports sur le cloud)
- **PowerBI Report Server** (Héberger les rapports sur des serveurs privés / au sein de notre entreprise)
- **PowerBI Mobile** 