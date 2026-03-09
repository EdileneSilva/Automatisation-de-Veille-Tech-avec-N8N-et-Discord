# Tech Watch Automation with n8n

### Présentation du projet

Ce projet est un système automatisé de **veille technologique** construit avec **n8n**.

### Technologies utilisées

* n8n (automatisation de workflows)
* Docker (pour exécuter n8n en local)
* Discord (pour les notifications)
* Flux RSS (sources de données)

### Architecture du projet

Le workflow suit la logique suivante :

Schedule Trigger  
↓  
Lecture des flux RSS  
↓  
Filtrage des articles publiés dans les dernières 24 heures  
↓  
Formatage des données des articles  
↓  
Envoi des articles vers Discord  

Cela permet au serveur Discord de recevoir automatiquement les articles publiés dans les dernières 24 heures.

### Sources RSS

Flux RSS utilisés dans ce projet :

* https://www.stat4decision.com/fr/feed/
* https://blog.octo.com/feed/
* https://medium.com/feed/tag/data-engineering
* https://practicaldataengineering.substack.com/feed
* https://towardsdatascience.com/feed

### Lancer le projet en local

Le projet utilise **Docker Compose** pour exécuter n8n en local.

Assurez-vous d'abord que Docker est installé.

Ensuite démarrez le conteneur avec :

docker compose up -d

Après cela, ouvrez n8n dans votre navigateur :

http://localhost:5678

Vous pouvez ensuite importer le workflow et l'activer.

### Structure du repository
```
project-folder
│
├── README.md
├── Screenshot
│ └── Screenshot.png
└── workflows
├── llm_worfflows.json
└── rss_workflows.json
```

### Export des workflows

Les workflows peuvent être exportés directement depuis **n8n** au format JSON et stockés dans le repository.

Cela permet à n'importe qui d'importer le workflow et d'exécuter la même automatisation.

### Intégration Discord

Les articles sont envoyés automatiquement vers un **canal Discord** en utilisant un webhook ou l’intégration Discord dans n8n.

Chaque message contient des informations comme :

* le titre de l’article
* le lien vers l’article
* une courte description

