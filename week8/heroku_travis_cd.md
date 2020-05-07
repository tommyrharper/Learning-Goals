# Heroku Travis-CD
This command sets up travis in heroku
```
travis setup heroku
```

Run this to get a token
```
heroku auth:token
```
Then encrypt it using this.
```
travis encrypt 'token' pasteAPIKeyHere --add deploylapi_key --pro
```

# Setting up Heroku

Go to heroku.com

Sign up

Go onto master branch on your machine
```
heroku create
```
You may have to now login to heroku

Use this command to check that the remote was added to your project:
```
git config --list | grep heroku
```

```
git push heroku master
```
This should push it all to heroku.

Type this to see where your heroku remote location is.

```
git remote -v
```
For trouble shooting

```
heroku logs
```
Run this to set up the database
```
heroku run rake db:migrate
```
Then this to open the application
```
heroku open
```


## Continuous Deployment

How to see it has worked?

Look at when the last deployment was added on heroku.

Get the A


