
 ## Introduction 
Le projet d'exploration de données météorologiques utilise l'API OpenWeather pour récupérer les données météorologiques des villes françaises et les stocker dans une base de données Cassandra. Il comprend trois composants principaux : la base de données Cassandra, le service de crawling et le service Flask API.



## Architecture et outils de projet 

#### Base de données Cassandra : 
Elle est configurée pour fonctionner sur le port 9042 et est accessible via le nom d'hôte **'cassandra'** dans le réseau Docker. Un script d'initialisation crée un espace de clés et une table pour stocker les données météorologiques.

#### Service de Crawling : 
Ce service, développé en Python, récupère les données météorologiques de l'API OpenWeather et les insère dans la base de données Cassandra. Un Dockerfile définit les dépendances nécessaires et le script **crawler.py** gère la récupération et l'insertion des données.

#### Service API : 
Également développé en Python, ce service extrait les informations météorologiques de la base de données Cassandra et répond aux requêtes de l'API. Le script **main.py** définit les endpoints de l'API et interroge la base de données pour récupérer les données météorologiques demandées.

#### Docker
Le projet utilise Docker Compose pour orchestrer la communication entre les différents composants et assure que la base de données Cassandra, le service de **crawling** et le service API sont tous lancés et opérationnels. Pour exécuter le projet, il suffit de se rendre dans le répertoire du projet et d'exécuter la commande **'docker-compose up'**.



#### Conclusion 

En résumé, le projet récupère les données météorologiques à partir de l'API OpenWeather, les stocke dans une base de données Cassandra et fournit une API pour interroger ces données.
































