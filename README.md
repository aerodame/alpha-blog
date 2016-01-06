##Notes
This is the repo for the first RoR project application from the Udemy course.

##Heroku Setup & Commands
Install Heroku Toolbelt in Nitrous and check the version
```
$ wget https://community.nitrous.io/docs/heroku-toolbelt
$ heroku version
```
Create a project and capture the URL name
```
$ heroku create
Creating frozen-fjord-4034... done, stack is cedar-14
https://frozen-fjord-4034.herokuapp.com/ | https://git.heroku.com/frozen-fjord-4034.git
Git remote heroku added
```

```
$ heroku keys:add
```
Found an SSH public key at /home/nitrous/.ssh/id_rsa.pub
Would you like to upload it to Heroku? [Yn] Y
Uploading SSH public key /home/nitrous/.ssh/id_rsa.pub... done

## Deploy now to Heroku
git push heroku master