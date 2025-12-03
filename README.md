TP 19 : Orchestration de microservices avec Spring Cloud: Eureka, Gateway et OpenFeign

📌 Introduction
Ce TP illustre comment orchestrer plusieurs microservices à l’aide de l’écosystème Spring Cloud, notamment :
Eureka pour la découverte de services
Spring Cloud Gateway pour le routage et le point d’entrée unique
OpenFeign pour la communication inter-services
Spring Cloud LoadBalancer pour la répartition de charge
H2 Database pour un stockage léger en mémoire
L’objectif est de comprendre et de mettre en œuvre une architecture microservices complète, flexible, scalable et résiliente.
🏗️ Architecture Globale
Client → Gateway → Eureka → LoadBalancer → Microservices
                      ↑
                 Services register

🔹 Services à mettre en place
Service	Rôle	Port
Eureka Server	Registre de services	8761
SERVICE-CLIENT	CRUD Client (H2)	8088
SERVICE-VOITURE	Gestion Voitures + Appels Feign vers Client	8089
API Gateway	Point d’entrée unique	8888
🚀 Fonctionnalités clés
✔️ Service Discovery (Eureka)

Les microservices s’enregistrent automatiquement.

Le registry fournit les adresses dynamiques aux clients.

✔️ API Gateway

Point d’entrée unique pour toutes les APIs.

Routage statique puis dynamique (lb://SERVICE-NAME).

Possibilité de filtrage, CORS, sécurisation.

✔️ OpenFeign

Appels REST simplifiés avec des interfaces Java.

Communication entre services via noms logiques.

✔️ Load Balancing

Distribution intelligente des requêtes entre instances.

Pas de dépendance aux adresses IP statiques.

📦 Technologies Utilisées

Spring Boot

Spring Cloud Netflix Eureka

Spring Cloud Gateway

Spring Cloud OpenFeign

Spring Cloud LoadBalancer

Lombok

H2 Database

Maven

📁 Structure du Projet
/eureka-server
<p align="center">
  <img src="https://github.com/YASSMINEOUQUELLI12/TP19/blob/main/eureka-server/eureka/tp19.PNG" width="500">
</p>

/service-client
<p align="center">
  <img src="https://github.com/YASSMINEOUQUELLI12/TP19/blob/main/service-client/eureka/TP19%20client1.PNG" width="500">
  <img src="https://github.com/YASSMINEOUQUELLI12/TP19/blob/main/service-client/eureka/TP19%20client.PNG" width="500">
</p>
/gateway
<p align="center">
  <img src="https://github.com/YASSMINEOUQUELLI12/TP19/blob/main/GateWay/TP19CLIE.PNG" width="500">
</p>



Chaque module est indépendant et contient son propre application.properties ou application.yml.
