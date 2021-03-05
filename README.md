# VOCAB-API

### To-do steps

1. **Create a file db.json**

```json
{
  "topic": [
    {
      "color": [
        {
          "vocab": "yellow",
          "pronunciation": "/ˈjeləʊ/",
          "photo": "asset/image/1.jpg",
          "audio": "asset/audio/1.mp3"
        },
        ...
```

2. **Install json with MacOS and let json-server watch the data file**

```bash
$ sudo npm i -g json --registry https://registry.npmjs.org/
$ json-server --watch db.json
```

_You will get json at https://localhost:3000_

3. **Add package.json, package-lock.json, json-server**

```bash
$ npm init -y
$ npm i
$ npm i json-server --registry https://registry.npmjs.org/
```

4. **Write a script at package.json**

```json
...
"script": {
    "start": "node server.js"}
```

5. **Create a file server.js**

```js
const jsonServer = require('json-server')
const server = jsonServer.create()
const router = jsonServer.router('db.json')
const middleWares = jsonServer.defaults()
const port = process.env.PORT || 3000

server.use(middleWares)
server.use(router)
server.listen(port)
```

6. **Add .gitignore**

```gitignore
node_modules
```

7. **Push git**

```bash
$ git init
$ git add .
$ git commit -m "initial commit"
$ git remote add origin https://github.com/mwhocodes/name-of-app.git
$ git push -u origin master
```

8. **Install Heroku and deploy app to heroku**

```bash
$ brew install heroku/brew/heroku
$ heroku --version
$ heroku create name-of-app
$ heroku login
$ git push heroku master
$ heroku open
```

Let see the result: [my-vocab-api](https://tranquil-forest-22446.herokuapp.com/topic)
