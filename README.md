6. Questions de compréhension
1. @SpringBootApplication regroupe trois annotations :
- @Configuration : déclare la classe comme source de configuration.
- @EnableAutoConfiguration : active la configuration automatique.
- @ComponentScan : recherche les composants dans le package et ses sous-packages.
Si le contrôleur est dans un package frère, il ne sera généralement pas détecté automatiquement.

2. L’auto-configuration permet à Spring Boot de configurer automatiquement l’application selon les dépendances présentes. Par exemple, avec spring-boot-starter-webmvc, Spring configure les éléments nécessaires pour créer une application web MVC.

3. ./mvnw spring-boot:run lance l’application avec Maven, tandis que java -jar target/...jar lance le fichier JAR compilé. DevTools est généralement actif dans le premier cas, mais désactivé par défaut dans le JAR de production.

4. Le mot de passe généré change à chaque démarrage pour éviter d’utiliser toujours les mêmes identifiants par défaut. On le personnalise pour faciliter l’accès et contrôler les identifiants de l’application.

5. L’ordre de priorité simplifié est : argument de ligne de commande > variable d’environnement > application.properties > valeur par défaut. Avec --server.port=9090, l’application utilise le port 9090.

6. management.info.env.enabled=true autorise l’affichage des propriétés info.* dans /actuator/info. Cette URL renverrait notamment le nom, la description et la version de l’application.

7. Exposer /actuator/beans ou /actuator/env sans authentification peut révéler des informations internes et des données sensibles, facilitant les attaques.

8. @RestController combine @Controller et @ResponseBody. @ResponseBody seul indique que le résultat d’une méthode doit être envoyé directement dans la réponse HTTP, généralement avec un autre contrôleur.
