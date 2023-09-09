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


## Les environnements
**Utilité :** Séparer la production du développement afin d’avoir des sources de données et des applications différentes (notamment si les apps ne sont pas testées ou validées).

**Les solutions** permettent de transporter les développements d’un environnement à un autre.

Par défaut, nous travaillons dans l’environnement Production.
Lorsque nous développons une application, il vaut mieux travailler avec différents environnements, notamment un environnement “de développement” puis passer à celui de production.

Pour **créer un nouvel environnement** : Aller au Power Platform admin center puis sur Environnements ⇒ New.

L’**environnement Developer** est réservé à un unique développeur et personne ne peut y être invité. <br>
**Production** est collaboratif, il est possible d’en créer plusieurs afin d’avoir de donner l’accès à différents groupes de personnes. <br>
**Sandbox** est un environnement qu’il est possible de copier ou réinitialiser.

**Note :** Il est préférable de toujours créer des objets dans une solution plutôt que dans un environnement. Cela permet notamment de définir correctement le publisher.