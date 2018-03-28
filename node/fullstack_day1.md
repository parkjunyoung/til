# express 기본 설치 후

```
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send({ hi: 'there' });
});

const PORT = process.env.PORT || 5000;
app.listen(PORT);
```

# 하루쿠 서버 체크

[https://devcenter.heroku.com/articles/getting-started-with-nodejs\#deploy-the-app](https://devcenter.heroku.com/articles/getting-started-with-nodejs#deploy-the-app)

동적 포트 체크

1. engines 등록

2. package.json 에 엔진등록

3. \`\`\`

   # package.json

4. 스크립트 체크

```
engines": {
       "node": "8.1.1",
       "npm": "5.0.3"
     },
```

# package.json

"scripts": {  
    "test": "node index.js"  
},

```
4. gitignore 등록
```

node\_modules

```
Express Prot 동적 체크
```

`const PORT = process.env.PORT`

# Git Add & Commit

```
git add *(.)
git commit -m 'init'
```

## Deploy the app

In this step you will deploy the app to Heroku.

Create an app on Heroku, which prepares Heroku to receive your source code.

```
$ 
heroku create

Creating sharp-rain-871... done, stack is cedar-14
http://sharp-rain-871.herokuapp.com/ | https://git.heroku.com/sharp-rain-871.git
Git remote heroku added
```

When you create an app, a git remote \(called`heroku`\) is also created and associated with your local git repository.

Heroku generates a random name \(in this case`sharp-rain-871`\) for your app, or you can pass a parameter to specify your own app name.

Now deploy your code:

```
$ 
git push heroku master

Counting objects: 343, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (224/224), done.
Writing objects: 100% (250/250), 238.01 KiB, done.
Total 250 (delta 63), reused 0 (delta 0)
remote: Compressing source files... done.
remote: Building source:
remote:
remote: -----
>
 Node.js app detected
remote:
remote: -----
>
 Creating runtime environment
remote:
remote:        NPM_CONFIG_LOGLEVEL=error
remote:        NPM_CONFIG_PRODUCTION=true
remote:        NODE_MODULES_CACHE=true
remote:
remote: -----
>
 Installing binaries
remote:        engines.node (package.json):  5.9.1
remote:        engines.npm (package.json):   unspecified (use default)
remote:
remote:        Downloading and installing node 5.9.1...
remote:        Using default npm version: 2.7.4
       ....
remote: -----
>
 Build succeeded!
remote:        ├── ejs@2.4.1
remote:        └── express@4.13.3
remote:
remote: -----
>
 Discovering process types
remote:        Procfile declares types -
>
 web
remote:
remote: -----
>
 Compressing... done, 9.4MB
remote: -----
>
 Launching... done, v8
remote:        http://sharp-rain-871.herokuapp.com deployed to Heroku
To https://git.heroku.com/nameless-savannah-4829.git
 * [new branch]      master -
>
 master
```

The application is now deployed. Ensure that at least one instance of the app is running:

```
$ 
heroku ps:scale web=1
```

Now visit the app at the URL generated by its app name. As a handy shortcut, you can open the website as follows:

```
$ 
heroku open
```


