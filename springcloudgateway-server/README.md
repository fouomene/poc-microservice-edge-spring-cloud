# poc-microservice-edge-spring-cloud
Mise en oeuvre de l'architechture Microservice avec Spring Cloud et ses Edge Microservices :

- **Spring Cloud Bootstrap** (e.g. Bootstrap context and @RefreshScope)

- **Spring Cloud Config** : Se positionne comme serveur de distribution des fichiers de configuration.
	- **Config Server**
	- **Config Client**
	
- **Spring Cloud Netflix** 
	- **Discovery** : Permet de découvrir les Microservice sur notre serveur. C’est aussi un outil clé pour la gestion des Microservices.
		- **Eureka Server**
		- **Eureka Client**
	- **Load Balancer**
		- **Ribbon** (config et dependance commenté) : Équilibrer les requêtes entre plusieurs instances pour éviter une surcharge d’un serveur
	- **Circuit Breaker** : Définit un ensemble de seuils qui, une fois dépassés, arrêteront l'exécution d'un bloc de code. 
		- **Hystrix** : Une API pour la résilience d’applications.
	
- **Spring Cloud Routing**
    - **Gateway** : Le point d’entrée unique pour les API et Microservices.
	- **OpenFeign** : Faire communiquer (synchrone) les microservices grâce à Feign.
	
- **Spring Cloud Load Balancer** : Équilibrer les requêtes entre plusieurs instances pour éviter une surcharge d’un serveur
	
- **Spring Cloud Observability**
    - **Sleuth** : Permet de donner des ID uniques à chaque requête, c'est 
	- **Zipkin** Client : permet exposer les traces vers Zipkin Server.
	
- **Spring Boot Actuator** : expose une API qui donne des informations sur le microservice concerné, mais ne propose pas d'interface graphique.

- **Zipkin Server** : permet de tracer les requêtes de service en service uniquement si ces services intègrent ses dépendances.


# Step 1 : Télécharger et Démarrer Zipkin Server
	curl -sSL https://zipkin.io/quickstart.sh | bash -s
	java -jar zipkin.jar

# Step 2 : Demarrer les différents microservices.
	mvn spring-boot:run
Ordre recommandé
- config-server
- eureka-server
- springcloudgateway-server
- microservice-produits (deux instances Ex port 8001,8011)
- microservice-commandes
- microservice-paiement
- clientui





