# Heroku-Help

- The Heroku CLI requires Git. Make sure you already have git installed. 
- If not, check https://github.com/Priya-wd/Git-Help

## Download & Install Heroku
- Windows OS: [Click here to Download](https://cli-assets.heroku.com/heroku-x86.exe)
- Mac OS: `$ brew tap heroku/brew && brew install heroku`
- Ubuntu 16+ : `$ sudo snap install --classic heroku`

**Verify Installation**
```
$ heroku --version
```

## Procfile or Start Script
> First, Heroku looks for a Procfile specifying your process types.

**Create Procfile** 
```
$ touch Procfile
```
> Open Procfile & Write
```
web: node app.js
```
> If no Procfile is present in the root directory of your app during the build process, your web process will be started by running npm start, a script you can specify in **`package.json`** like:

**package.json**
```
"scripts": {
  "start": "node app.js"
}
```
## Port Variable
Make sure you have set PORT variable 
```
var PORT = process.env.PORT || 3000
```

## Build your app and run it locally
Before deploying app to Heroku, you can check it locally
```
$ npm install
$ heroku local web
```
> Your app should now be running on `http://localhost:5000/`

## Deploy Node.js Application on Heroku
Run following commands to deploy your app on Heroku
```
$ git add .
$ git commit -m "Added a Procfile or Start Script"

$ heroku login -i
$ heroku create
$ git push heroku master
```
> Go to Heroku site & refresh. You will see your app added to Heroku

To open the app in your browser, run
```
$ heroku open
```
