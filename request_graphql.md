## Créer un utilisateur
```
  mutation {
    createUser(user: { username: "testuser", email: "test@tesl.com", password: "TestPassword"}) {
      username
      email
    }
  }
```

## Récupérer les utilisateur
```
  query {
    users {
      _id
      username
      email
    }
  }
```
## Créer un article 
### Attention il s'agit de _id de mon author a changer de votre côté ``
  ```
  mutation {
    createArticle(article: {title: "test@tesl.com", description: "TestDescription", 
    body:"testboy1", tagList:["tada", "toto", "tutu"], author:"5edb4a873e429d1fb8eab02d"}) {
      _id
      title
      tagList
      author{username}
    }
  }
```


## Récupérer les articles
```
  query{
    articles{
    _id
    title
    description
    body
    tagList
    author{username}
    }
  }
```


## Créaction d'un Comment
### Attention ce sont mes _id vous devrez les changer par les votre de votre DB
```
  mutation{
    createComment( comment:{body:"WOUAHHHHH c'est au top",
    author:"5edb4a873e429d1fb8eab02d", article:"5edb56b57bf5bb2788c62963"}){
      body
      author{username}
    }
  }
```
## Récupérer la liste des articles et leur commentaire
Example : 
```
  query{
    article(_id:"5edb51607c995f2c54a85397"){
      title
      comments{body}
      description  	
    }
  }
```
```
query{
  articles{
	_id
  title
  description
  body
  tagList
  author{username} #Attention il faut la dernière feature pour que cela fonctionne
  comments{body}
	}
}
```
## BONUS
### Récupérer les trois permiers articles par date de création 
# WIP

### Implémenter une query permettant d'effectuer une recherche sur le body d'un article et le body d'un commentaire
``` 
  query {
    search(value: "test"){
      ...on Article{
        body
      }
      ... on Comment{
        body
      }
    }
  }
'''