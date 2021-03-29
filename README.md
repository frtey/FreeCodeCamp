# FreeCodeCamp
Collection de liens vers mon dépôt Repl.it, constitué de projets FreeCodeCamp, avec explication de chaque projet

Lien général vers le dépôt : https://replit.com/@frtey

1. [APIs and Microservices Projects](#1-apis-and-microservices-projects)
2. [Quality Assurance](#2-quality-assurance)
3. [Scientific Computing with Python](#3-scientific-computing-with-python)

## 1. APIs and Microservices Projects

**Ces projets m'ont permis d'aborder la construction d'un serveur de microservice en Javascript Node.js, ainsi que l'utilisation de certaines de ses bibliothéques les plus utiles, comme Express ou Mongoose. J'ai également pu explorer le fonctionnement (création, mise à jour et interrogation) d'une base de données noSQL (MongoDB en l'occurence) ce qui était nouveau pour moi, ayant plutôt l'habitude du SQL, ainsi que de Mongoose, de sa syntaxe et de son système de schémas et models. Enfin, j'en ai également plus appris sur le fonctionnement des APIs, de ses méthodes GET et POST, et de comment articuler les routes et réponses via Express.**

**Les principaux problèmes rencontrés durant mon travail auront été, outre la compréhension de nouvelles technologies et bibliothèques, la validation des tests sur certains projets, due à ma mauvaise lecture de certaines specifications. J'ai également mis beaucoup trop de temps à trouver une solution pour récupérer les metadonnées de fichiers uploadés (dernier projet), avant de trouver Multer, puis de remarquer, par la suite, que cette bibli était suggérée par l'énoncé de FCC depuis le début... Là encore, un problème de rigueur sur ma lecture des énoncés, que j'ai pris soin de palier par la suite.**

### a) <ins>Timestamp Microservice</ins>

https://replit.com/@frtey/boilerplate-project-timestamp

<ins>But du projet</ins> : Gérer un appel API vers api/timestamp/{date}, où {date} est une date valide (ou l'instant présent si non renseignée). L'appel renvoie un doc JSON avec la date donnée aux formats Unix et UTC

### b) <ins>Request Header Parser Microservice</ins>

https://replit.com/@frtey/boilerplate-project-headerparser

<ins>But du projet</ins> : Retourner un json de l'appel vers /api/whoami, contenant l'adresse ipv6 de l'utilisateur, son langage préféré, ainsi que ses informations de navigateur

### c) <ins>URL Shortener Microservice</ins>

https://replit.com/@frtey/boilerplate-project-urlshortener

<ins>But du projet</ins> : Recevoir du client en POST une adresse URL envoyée vers /api/shorturl/new, si l'adresse est valide, l'enregistrer dans une BDD, et renvoyer vers le client un json avec l'adresse longue et l'adresse courte. Si l'api appelée est /api/shorturl/{shorturl}, rediriger vers le site correspondant.
  
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

## 2. Quality Assurance

**NOTE: A chaque exercice et avant l'écriture du code lui-même, des tests unitaires et fonctionnels ont été écrits. Comme je l'ai fait pour chaque projet, je ne le reprécise pas dans les descriptions**

**Cette série de projets m'aura permis, en plus d'explorer plus en profondeur Node/Express, de découvrir le principe des tests unitaires et fonctionnels, ainsi que les technologies associées à ce domaine (ici, Mocha et Chai). Ces techniques m'étaient totalement incoonues, et les ecrire avant le code m'aura permis de réfléchir, de planifier et de structurer mon code avant même d'en écrire un mot. Au final, la qualité de mon code s'en est beaucoup fait ressentir (positivement bien sûr).**

**Si les trois premiers projets et le traducteur étaient relativement simple, le Sudoku solver aura été le plus challengant des 10aines de projets effectués sur FCC. Après avoir trouvé une solution fonctionelle mais qui ne me satisfaisait aucunement de par sa complexité et sa longueur, j'ai repris tout ou presque à zero. Après des recherches, j'ai réecrit la solution en utilisant une fonction récursive, solution qui ne m'étais jamais venue à l'esprit, puisque je ne l'avais jamais réellement comprise auparavant. Cela m'aura permis de bien mieux comprendre le concept de récursivité, et surtout de ne jamais avoir peur de se débarasser complétement d'un mauvais code : développer la solution recursive m'aura pris 5 fois moins de temps que de développer ma première solution, pour un résultat bien meilleur.**

### a) <ins>Metric-Imperial Converter</ins>

https://replit.com/@frtey/boilerplate-project-metricimpconverter

<ins>But du projet</ins> : A partir de l'input d'un utilisateur comprenant un flottant et une unité, envoyé en GET vers /api/convert, valider l'input, effectuer des opérations de conversions d'unité (miles <-> kms; gallons <-> litres; pounds <-> kgs), et renvoyer au client un json avec nombre initial, unité initiale, nombre converti, unité convertie et chaine de caractères rassemblant toute ces informations. Enfin, ecrire tests unitaires et fonctionnels validant le code et le service.

### b) <ins>Issue Tracker</ins>

https://replit.com/@frtey/boilerplate-project-issuetracker

<ins>But du projet</ins> : Service permettant à des utilisateurs (employés par exemple), de soumettre un ticket, de le mettre à jour et de le supprimer.
* Un POST envoyé à /api/issues/{projectname} créera un ticket dans la BDD, et renverra au client un json avec les éléments du document créé.
* Un GET renverra le document correspondant au projectname, avec une liste des tickets correspondants.
* Un PUT updatera ce ticket avec les éléments mentionnés, et renverra un message de succès et l'id du document modifié, ou un message d'erreur si erreur de BDD ou id manquant.
* UN DELETE supprimera ce ticket, et renverra un message de succès et l'id du document supprimé, ou un message d'erreur si erreur de BDD ou id manquant.


### c) <ins>Personal Library</ins>

https://replit.com/@frtey/boilerplate-project-library

<ins>But du projet</ins> : Possiblité de créer une entrée de livre avec POST /api/books, de créer un commentaire sur un certain livre avec POST /api/books/{bookid} ou de supprimer un livre ou tout les livres avec DELETE.

### d) <ins>Sudoku Solver</ins>

https://replit.com/@frtey/boilerplate-project-sudoku-solver

<ins>But du projet</ins> : Permet de résoudre une grille Sudoku automatiquement. l'utilisateur fournit au programme une chaine de 81 caractères, composée de points et de chiffres devant être compris entre 1 et 9. A chaque nouveau caractère rentré par l'utilisateur, la grille de Sudoku refléte automatiquement la donnée. En appuyant sur le bouton Solve, le client POST la chaine vers /api/solve. Le serveur résout la grille, et la renvoie au client (ou renvoie un message d'erreur si la chaine est trop longue ou si des caractères illégaux sont présent). Un autre module du service permet à l'utilisateur de vérifier si une case donnée peut contenir un chiffre donné.


### e) <ins>American / British Translator</ins>

https://replit.com/@frtey/boilerplate-project-american-british-english-translator

<ins>But du projet</ins> : En rentrant une chaine de caractères, l'utilisateur peut voir si une traduction anglais d'Angleterre <-> anglais des USA existe. La chaine est donc envoyée au serveur, ainsi que le sens de traduction, et un programme parcourt la chaîne mot par mot et cherche la traduction du mot courant. Il renvoie la chaîne avec les traductions surlignés en vert, et remplacant les mots traduits.


## 3. Scientific Computing with Python

### a) <ins>Arithmetic Formatter</ins>

https://replit.com/@frtey/boilerplate-arithmetic-formatter

<ins>But du projet</ins> : Formater un input utilisateur : une série de calculs arithmétiques, entre 1 et 5 calculs, doivent être retournés sous forme de calculs posés. Seuls les soustractions et additions sont acceptés.
Par exemple :
```
arithmetic_arranger(["3 + 855", "3801 - 2", "45 + 43", "123 + 49"], True)
```
retournera :
```
    3      3801      45      123
+ 855    -    2    + 43    +  49
-----    ------    ----    -----
  858      3799      88      172
```
