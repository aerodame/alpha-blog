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

###Let's change the name
```
$ heroku rename alpha-blog-aerodame
=> Renaming frozen-fjord-4034 to alpha-blog-aerodame... done
=> https://alpha-blog-aerodame.herokuapp.com/ | https://git.heroku.com/alpha-blog-aerodame.git
```

###Migrations, rollbacks and additions
There are a couple of paths here when creating tables, atrributes(columns), and edits.  First way is to use ```rake generate migration create<tablename>``` and then the next would be to use ```rake generate add```
The first method:
```$ rake generate migration create_articles```
=> creates a migration file : <datetime>_create_articles.rb

The resulting migration file is:
```
class CreateArticles < ActiveRecord::Migration
  def change
    create_table :articles do |t|
      t.string :title
    end
  end
end

$ rake db:migrate
```

Oops... we forgot to add our description column to the table.  So we can rollback the migration and re-enter the column and regenerate.

```
$ rake db:rollback

class CreateArticles < ActiveRecord::Migration
  def change
    create_table :articles do |t|
      t.string :title
      t.text :description
    end
  end
end
```
