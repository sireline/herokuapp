# herokuapp

# 作業の流れ

## GitHubリポジトリ作成

```txt
git clone https://github.com/ユーザ名/アプリ名.git
```

## アプリ制作

<details>
  <summary>サンプルコード</summary>

index.html

```html
<!DOCTYPE html>
<html lang="ja">
    <head>
        <meta charset="utf-8">
        <title>Node App on Heroku</title>
    </head>
    <body>
        <H1>Hello Heroku.</H1>
    </body>
</html>
```

index.js

```javascript
const express = require("express");
const app = express();

app.use(express.static("public"));
app.get("/",function(req,res){
  res.sendFile(__dirname+"/index.html");
});

app.listen(process.env.PORT || 5000, function(){
  console.log("The server is runnning on port 5000.");
});
```

Procfile

```txt
web: node index.js
```

package.json

```json
{
  "name": "herokuapp",
  "version": "1.0.0",
  "description": "heroku test app",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "engines": {
    "node": "12.x"
  },
  "dependencies": {
    "express": "^4.15.2"
  },
  "author": "",
  "license": "MIT"
}
```

.gitignore

```txt
/node_modules
npm-debug.log
.DS_Store
/*.env
```
</details>

## node.jsアプリ初期化

```txt
nmp init
npm install
```

## ローカルテスト

```txt
heroku local web
```

- [localhost:5000](http://localhost:5000)

## Herokuアプリ作成

```txt
heroku login
heroku create
```

## Herokuアプリコミット

```txt
git add .
git commit -m "heroku test"
```

## Herokuへデプロイ

```txt
git push heroku master
```

## Herokuアプリ起動

```txt
heroku open
```
