
## Docs

- https://thepythoncode.com/article/fullstack-notes-app-with-fastapi-and-reactjs
  
## Front End

- https://github.com/sanogotech/NotesAppFrontend-FastAPI-React


FastAPI est un framework web moderne et rapide (haute performance) pour construire des API avec Python 3.6+ basé sur les annotations de type standard Python. Il est conçu pour être facile à utiliser et à apprendre. Il fournit également une validation automatique des requêtes et des réponses à l'aide de Pydantic, ainsi que des fonctionnalités OpenAPI pour la documentation de l'API.

Voici un exemple simple pour créer une API avec FastAPI :

Installation : Tout d'abord, vous devez installer FastAPI et un serveur ASGI, Uvicorn, qui permettra de servir votre application. Vous pouvez les installer en utilisant pip :

```bash
pip install fastapi uvicorn
```

Création de l'API : Ensuite, créez un fichier, par exemple main.py, et ajoutez le code suivant pour créer une API de base :

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def read_root():
    return {"Hello": "World"}

@app.get("/items/{item_id}")
async def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "q": q}
```

Dans cet exemple, nous avons créé deux routes :

Une route racine ("/") qui retourne simplement un message de bienvenue.
Une route ("/items/{item_id}") qui prend un paramètre item_id en chemin et un paramètre facultatif q en query pour retourner les deux dans une réponse.
Lancement de l'API : Pour lancer l'API, ouvrez votre terminal, naviguez vers le répertoire où se trouve votre fichier main.py, et exécutez :

```bash
uvicorn main:app --reload
```

L'option --reload fait que le serveur redémarre automatiquement après chaque modification du code, ce qui est utile pendant le développement.

Testez votre API : Une fois l'API lancée, vous pouvez y accéder en allant sur http://127.0.0.1:8000 dans votre navigateur. Vous pouvez également accéder à la documentation interactive générée par FastAPI à http://127.0.0.1:8000/docs où vous pourrez tester vos endpoints directement depuis le navigateur.
C'est un exemple très basique. FastAPI offre bien plus de fonctionnalités, comme la gestion des requêtes POST, la validation des données entrantes, la sécurité et l'authentification, les dépendances, etc. Je vous encourage à consulter la documentation officielle de FastAPI pour explorer toutes les possibilités qu'offre ce framework.






