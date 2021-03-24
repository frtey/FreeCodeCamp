# FreeCodeCamp
Collection de liens vers mon dépôt Repl.it, constitué de projets FreeCodeCamp, avec explication de chaque projet

Lien général vers le dépôt : https://replit.com/@frtey

## 1. <ins>APIs and Microservices Projects</ins>

**Ces projets m'ont permis d'aborder la construction d'un serveur de microservice en Javascript Node.js, ainsi que l'utilisation de certaines de ses bibliothéques les plus utiles, comme Express ou Mongoose. J'ai également pu explorer le fonctionnement (création, mise à jour et interrogation) d'une base de données noSQL (MongoDB en l'occurence) ce qui était nouveau pour moi, ayant plutôt l'habitude du SQL, ainsi que de Mongoose, de sa syntaxe et de son système de schémas et models. Enfin, j'en ai également plus appris sur le fonctionnement des APIs, de ses méthodes GET et POST, et de comment articuler les routes et réponses via Express.**

**Les principaux problèmes rencontrés durant mon travail auront été, outre la compréhension de nouvelles technologies et bibliothèques, la validation des tests sur certains projets, due à ma mauvaise lecture de certaines specifications. J'ai également mis beaucoup trop de temps à trouver une solution pour récupérer les metadonnées de fichiers uploadés (dernier projet), avant de trouver Multer, puis de remarquer, par la suite, que cette bibli était suggérée par l'énoncé de FCC depuis le début... Là encore, un problème de rigueur sur ma lecture des énoncés, que j'ai pris soin de palier par la suite.**

### a) <ins>Timestamp Microservice</ins>

https://replit.com/@frtey/boilerplate-project-timestamp

<ins>But du projet</ins> : Gérer un appel API vers api/timestamp/<date>, où <date> est une date valide (ou l'instant présent si non renseignée). L'appel renvoie un doc JSON avec la date donnée aux formats Unix et UTC

### b) <ins>Request Header Parser Microservice</ins>

https://replit.com/@frtey/boilerplate-project-headerparser

<ins>But du projet</ins> : Retourner un json de l'appel vers /api/whoami, contenant l'adresse ipv6 de l'utilisateur, son langage préféré, ainsi que ses informations de navigateur

### c) <ins>URL Shortener Microservice</ins>

https://replit.com/@frtey/boilerplate-project-urlshortener

<ins>But du projet</ins> : Recevoir du client en POST une adresse URL envoyée vers /api/shorturl/new, si l'adresse est valide, l'enregistrer dans une BDD, et renvoyer vers le client un json avec l'adresse longue et l'adresse courte. Si l'api appelée est /api/shorturl/<shorturl>, rediriger vers le site correspondant.
  
### d) <ins>Exercise Tracker</ins>

https://replit.com/@frtey/boilerplate-project-exercisetracker

<ins>But du projet</ins> : Créer un service de publication d'exercices. Plusieurs aspects à ce service :
* Un POST vers /api/exercise/new-user, créé par le formulaire d'inscription, enregistre l'utilisateur dans une BDD, et renvoie un json avec l'id et le pseudo de l'utilisateur
* Un GET vers /api/exercise/users interroge la BDD et renvoie un tableau avec les id et pseudo de tout les utilisateurs
* Un POST vers /api/exercise/add ajoute un exercice avec description, durée et date, à l'utilisateur indiqué
* Un GET vers /api/exercise/log?{userId}[&from][&to][&limit], permettant de récupérer les exercices d'un certain utilisateur, avec possibilités de limiter les résultats à un certain nombre, et de définir une plage temporelle

### e) <ins>File Metadata Microservice</ins>

https://replit.com/@frtey/boilerplate-project-filemetadata

<ins>But du projet</ins> : Recevoir du client en POST un fichier envoyé vers /api/fileanalyse, et renvoyer vers le client un json avec le nom du fichier, son type et sa taille.

## 2. <ins>Quality Assurance</ins>

**NOTE: A chaque exercice et avant l'écriture du code lui-même, des tests unitaires et fonctionnels ont été écrits. Comme je l'ai fait pour chaque projet, je ne le reprécise pas dans les descriptions**

### a) <ins>Metric-Imperial Converter</ins>

https://replit.com/@frtey/boilerplate-project-metricimpconverter

<ins>But du projet</ins> : A partir de l'input d'un utilisateur comprenant un flottant et une unité, envoyé en GET vers /api/convert, valider l'input, effectuer des opérations de conversions d'unité (miles <-> kms; gallons <-> litres; pounds <-> kgs), et renvoyer au client un json avec nombre initial, unité initiale, nombre converti, unité convertie et chaine de caractères rassemblant toute ces informations. Enfin, ecrire tests unitaires et fonctionnels validant le code et le service.

### b) <ins>Issue Tracker</ins>

https://replit.com/@frtey/boilerplate-project-issuetracker

<ins>But du projet</ins> : Service permettant à des utilisateurs (employés par exemple), de soumettre un ticket, de le mettre à jour et de le supprimer.
*Un POST envoyé à /api/issues/<projectname> créera un ticket dans la BDD, et renverra au client un json avec les éléments du document créé.
*Un GET renverra le document correspondant au projectname, avec une liste des tickets correspondants.
*Un PUT updatera ce ticket avec les éléments mentionnés, et renverra un message de succès et l'id du document modifié, ou un message d'erreur si erreur de BDD ou id manquant.
*UN DELETE supprimera ce ticket, et renverra un message de succès et l'id du document supprimé, ou un message d'erreur si erreur de BDD ou id manquant.
