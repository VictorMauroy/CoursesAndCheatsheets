# <span style="color: green"><u>**Microsoft Azure**</u></span>

Note: Made in french, must be translated...!

## Table des matières
* [**Description**](#description)
    - [Types de services](#azure-fournit-différents-services)
    - [Types de cloud](#azure-fournit-trois-types-de-cloud)
* [**Configurer Azure**](#configurer-azure)
    - [Vocabulaire](#vocabulaire)
    - [Choisir sa région](#choisir-sa-région)
    - [Abonnement](#abonnement)
    - [Utilisateurs](#utilisateurs)
    - [App registration](#app-registrations)

## **Description**
"Azure" est une plateforme de cloud computing fournie par Microsoft. Il offre un large éventail de services et de solutions pour la gestion, le stockage, le déploiement et la gestion d'applications et de services sur le cloud. (ChatGPT)

### Azure fournit différents services
- **Iaas** (Infrastructure as a Service). ⇒ *Créer et configurer de zéro* 

Il permet essentiellement de travailler sur une infrastructure (VM) mais aussi du stockage et gérer la couche réseau.

- **Paas** (Platform as a Service). ⇒ *Travailler directement sur une base fournie*

Avoir directement un serveur sur lequel nous pouvons travailler et envoyer notre code. On peut notamment le réaliser à travers “App Services” (possible de créer un site web). Cloud Provider gère à notre place le serveur utilisé pour héberger notre service.

- **Saas** (Software as a Service). ⇒ *Utiliser aisément des logiciels fournis*

Partie office 365. Pouvoir accéder à toute app/logiciel développé par Microsoft. 

### Azure fournit trois types de Cloud
- **Public** ⇒ *Ouvert à tous. On peut tous s’inscrire à ce cloud.*

*Avantage* : Coût le plus réduit car divisé entre chaque utilisateur. <br>
*Inconvénient* : La sécurité la plus faible car dépendant fortement des administrateurs et des utilisateurs.

- **Privé** ⇒ *Exclusivement dédié à une personne ou une entreprise.*

*Inconvénient* : Coût le plus élevé car assumé par un unique propriétaire. <br>
*Avantage* : Meilleure sécurité car coût assumé par une unique entité.

- **Hybride** ⇒ *Une partie des services en accès public, l’autre en privé. Rassemble deux clouds : un public et un privé.*

Ex: site web côté public, bdd côté privé. <br>
Permet de répartir les différentes ressources sur deux clouds selon ce que nous voulons partager ou non. Tout ce qui n’est pas critique sera sur le cloud public pour optimiser les coûts et tout ce qui est sensible restera sur un cloud privé pour garantir la sécurité des données.

- **Communautaire** ⇒ *Inscription sur critères spécifiques.*

Réservé à des communautés spécifiques, ex : un cloud réservé aux allemands ou aux chinois.



## **Configurer Azure**
Installer **Azure Stack Hub** afin de gérer du cloud local, privé voire hybride. <br>
Sinon Azure Stack HCI et Edge servent à compléter l’offre Azure Stack locale.

### Vocabulaire
Une **ressource Azure** est une instance d’un service. (Ex: créer une VM va instancier un service VM) 

Les **groupes de ressources** vont permettre de regrouper des ressources afin de répondre à un besoin donné. (ex : pour un site web : un app service, une bdd, un emplacement de stockage, etc.). Il sera aussi possible de gérer plus facilement les autorisations puisqu’il est possible d’en appliquer à un groupe de ressource.

### Choisir sa région
Selon la région choisie (US, EU, etc.) : 
- Les lois du territoire choisi seront appliquées
- Les prix varient (ex : coût de l’électricité)
- Certains services pourraient ne pas être disponibles
- Selon le datacenter choisi, il pourrait ne pas y avoir assez de stockage et nos données pourraient être réparties entre deux datacenters (pas super)

Il est possible de choisir sa zone dans une région lors de la création d’une VM. Pour de la haute disponibilité, il serait possible de créer plusieurs VM, toutes dans des régions différentes (prépare aux scénarios de panne).

### Abonnement 
La sélection de l’abonnement lors de l’utilisation d’un service va **indiquer sur quel budget il faudra prélever** de l’argent. Par exemple, si on veut que certaines ressources soient dédiées au marketing et d’autres aux formations. Ou quelle entreprise chez laquelle nous travaillons sera prélevée pour ce service.

Les **Management Group** permettent de regrouper des abonnements afin de plus facilement les retrouver/hiérarchiser.
Lors de la création d’abonnement, il faut préciser qui a le droit d’y accéder. Les Management Group permettent de facilement gérer cette option car on peut appliquer les droits ou assigner des utilisateurs à ces groupes.

Afin d’**ajouter un utilisateur à un abonnement**, il faut l’ajouter ou le créer (Users ⇒ Create user) et il sera ensuite possible de lui accorder des droits.

### Utilisateurs 
**Azure Active Directory** afin de voir les utilisateurs. <br> Afin de se connecter à Azure, c’est AAD qui va vérifier les login et mdp sur la majeure partie des applications. Le logiciel AAD Connect permet d’enregistrer et récupérer des utilisateurs locaux et de les exporter sur le cloud et ils seront synchronisés. 

**Il faut un compte Azure AD pour travailler en local et un autre à distance** (ce ne sont pas les mêmes comptes). Il est alors possible de faire en sorte que certaines personnes puissent travailler uniquement en local ou à distance. En **activant la synchronisation**, on peut faire en sorte que le compte distant et local utilisent les mêmes login et mdp.

### App registrations 
Permet de créer une identité à une application, cela permet de l’assigner sur d’autres ressources Azure et lui donner des droits, notamment à une base de données permettant une connexion automatique.