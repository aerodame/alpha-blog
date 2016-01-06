###Heroku Setup & Commands
Install Heroku Toolbelt in Nitrous and check the version
```
$ wget https://community.nitrous.io/docs/heroku-toolbelt
$ heroku version
```
Create a project and capture the URL name
```
$ heroku create
=> Creating frozen-fjord-4034... done, stack is cedar-14
=> https://frozen-fjord-4034.herokuapp.com/ | https://git.heroku.com/frozen-fjord-4034.git
=> Git remote heroku added
```

```
$ heroku keys:add
=> Found an SSH public key at /home/nitrous/.ssh/id_rsa.pub
=> Would you like to upload it to Heroku? [Yn] Y
=> Uploading SSH public key /home/nitrous/.ssh/id_rsa.pub... done
```
### Deploy now to Heroku
```
git push heroku master
=> Counting objects: 79, done.
=> Compressing objects: 100% (69/69), done.
=> Writing objects: 100% (79/79), 18.15 KiB | 0 bytes/s, done.
=> Total 79 (delta 9), reused 0 (delta 0)
=> remote: Compressing source files... done.
=> remote: Building source:
...
=> To https://git.heroku.com/frozen-fjord-4034.git
=> * [new branch]      master -> master
```

###Oops... let's change the name
```
$ heroku rename alpha-blog-aerodame
=> Renaming frozen-fjord-4034 to alpha-blog-aerodame... done
=> https://alpha-blog-aerodame.herokuapp.com/ | https://git.heroku.com/alpha-blog-aerodame.git
```