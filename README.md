# js-express-routes

## Start up : 

* créer votre projet
  
  * Créer votre repo sur github
  * Cloner votre projet (ex. git clone XXXXX)
  * cd XXXXX
  * npm init (répondre oui à toutes les questions)
  * touch index.js (création du fichier index.js)
  * atom . (pour ouvrir atom)

* installer express dans votre projet

  * npm install express --save

* créer un server express qui écoute en port 5000

  * cf. http://expressjs.com/fr/starter/hello-world.html

* démarrer le server avec node ou nodemon

  * Avec node : node index.js
  * Avec nodemon : nodemon index.js (n'oubliez pas d'ainstaller nodemon globalement avant : npm i -g nodemon)

## Exercices : 

### Exercice 1

Ecrire 3 routes :

* 1. GET / => 'Home page'
* 2. GET /users => 'liste d\'utilisateur' ex. http://localhost:5000/users
* 3. GET /users/:lenomdelutilisateur => l'le nom de l'utilisateur est : lenomdelutilisateur'

### Exercice 2

Pour les 3 routes, on veut, à présent, rendre du html à la place d'une simple string.

* 1. GET /users => renvoie une vrai liste d'utilisateur basé sur ce tableau

ex. Michel, Osman, Tandi

``` 
const users = [
  {id: 1, firstName: 'Osman', pseudoGithub: 'xxx'},
  {id: 2, firstName: 'Tandi', pseudoGithub: 'xxx'},
  {id: 3, firstName: 'Daniel', pseudoGithub: 'xxx'},
  {id: 4, firstName: 'Faustino', pseudoGithub: 'xxx'},
  {id: 5, firstName: 'Ijacques', pseudoGithub: 'xxx'}
]
``` 

* 2. GET /users/:id => renvoie le prénom de l'utilsateur qui à cet ID

### Exercice 3

* 1. Faire la même en html avec ejs :

``` 
Par exemple, pour GET /users, il faut renvoyer une liste html (<ul><li>...)
```

  * References EJS :

    * http://ejs.co/
    * http://expressjs.com/fr/guide/using-template-engines.html
  
* 2. Styliser votre rendu avec css

### Exercice 4 : Créer des routes qui gérent les projets github des utilisateur

1. créer un tableau js de projets avec la forme suivante :

``` 
const projects = [

 {
    id: 0,
    userId: 3, // le repo doit correspondre un utilisateur du tableau 'users'
    name: xxx
    githubUrl : xxxx
    githubRepo : xxxx
 },
 {
    id: 1,
    userId: 2, // le repo doit correspondre un utilisateur du tableau 'users'
    name: xxx
    githubUrl : xxxx
    githubRepo : xxxx
 },
 {
    id: 2,
    userId: 4, // le repo doit correspondre un utilisateur du tableau 'users'
    name: xxx
    githubUrl : xxxx
    githubRepo : xxxx
 }
];
``` 

2. faire une route /projects/ qui rend une liste html de tous les projets

3. faire une route /projects/:id qui rend une page de projet

4. Dans le rendu de la route /projects/, rajouter, pour chaque projet, le lien vers la page du projet correspondant (ex. /projects/0)

5. faire une route user/:userId/projects/ qui rend une liste html des projets d'un utilisateur

6. Dans le rendu de la route user/:userId/projects/, rajouter, pour chaque projet, le lien vers la page du projet correspondant (ex. /projects/0)

### Exercice 5 : Créer un middleware qui intercepte les errors et les écrit dans le terminal :

1. trouver le guide de creation de middleware
2. mettre en place un logger
3. mettre en place un middleware qui attrape les erreurs (chercher dans les middlewares existants de Expressjs)

### Exercice 6 : Gérer ses response

1. Trouver la doc de response de la librairie express
2. Créer 2 routes qui renvoie les même donnée en JSON qui /users et /users/:id. Les routes seront :
  
  * /api/users
  * /api/users/:id
  
3. Créer une route qui gére toutes les fausses routes (celles qui ne sont pas spécifiées par notre app) et qui renvoie un status 4O4.

### Exercice 7 : Base de données

1. installer posgresql
2. Tester des requetes SQL avec psql. (ex. CREATE DATABASE promo7)

  * ex. CREATE DATABASE promo7
  * ex. CREATE TABLE users
  * ex. INSERT ...
  * ex. SELECT * FROM users
  * ex. UPDATE ...
  * ex. DELETE
  
3. En utilisant le pg client (npm i -S pg), interroger votre base de données Postgresql via votre application express
4. Créer des routes express qui interagissent avec votre base :
  
  * ex. POST /user => INSERT ...
  * ex. GET /users => SELECT * FROM users
  * ex. PUT /user/:id => UPDATE ...
  * ex. DELETE /user/:id => DELETE
  
5. Tester vos routes avec PostMan ou CURL
6. Créer une page listant les users (en React ou EJS)
7. Créer une page avec un formlaire permettant de créer un user (en React ou EJS)
8. Utilser le même formulaire pour faire un update d'un user (en React ou EJS)
9. Dans la page liste, ajouter à chaque element un bouton "supprimer". Quand on clique sur un des bouton, ça supprime l'utilisateur correspondant.

10. Créer une table "projects" avec les colonnes suivantes:

    * id: PRIMARY KEY,
    * userId: INT, // correpond à un utilisateur du tableau 'users'
    * name: STRING
    * githubUrl : STRING
    * githubRepo : STRING

11. Repéter les étapes 4, 5, 6, 7, 8, 9 pour les projets. Attention un projet ne peut être créer sans un userID. En gros un projet est toujours lié à un user. un user peut avoir plusieurs projets et un projet ne peut appartenir qu'à un seul user (Relation ONE TO MANY)

12. Mettre votre appli et votre base sur HEROKU

Bon courage !!!


