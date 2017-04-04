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

Pour ça, nous allons utiliser un moteur de template : EJS.

EJS peut être utiliser en tant que middleware :
  
  * 

* 1. GET /users => renvoie une vrai liste d'utilisateur base sur ce tableau

ex. Michel, Osman, Tandi

const users = [
  {id: 0, firstName: 'Michel'},
  {id: 1, firstName: 'Osman'},
  {id: 2, firstName: 'Tandi'},
  {id: 3, firstName: 'Daniel'},
  {id: 4, firstName: 'Faustino'},
  {id: 5, firstName: 'Ijacques'}
]

* 2. GET /users/:id => renvoie le prénom de l'utilsateur qui à cet ID

### Exercice 3

* 1. Faire la même en html avec ejs :

``` 
Par exemple, pour GET /users, il faut renvoyer une liste html (<ul><li>...)
```

* References EJS :

  * http://ejs.co/
  * http://expressjs.com/fr/guide/using-template-engines.html
