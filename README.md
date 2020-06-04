## Initialisation du projet

- Création d'un nouveau repo git "graphql-articles"
- _git clone_
- `npm init -y`
- `package.json` => `"start": "nodemon --exec babel-node server/index.js"`
- `mkdir server`

## Installation des dépendences

- `npm i body-parser cors express express-graphql graphql graphql-tools graphql-yoga jsonwebtoken merge-graphql-schemas mongoose mongoose-unique-validator slug`

- `npm i -D @babel/cli @babel/core @babel/preset-env concurrently nodemon`

## Test du serveur : 

- `npm start`
- http://localhost:4000/playground

