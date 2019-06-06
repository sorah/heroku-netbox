# netbox Heroku setup

This repository is a [digitalocean/netbox](https://github.com/digitalocean/netbox) setup on Heroku.

```
heroku create
heroku addons:create heroku-postgresql:hobby-dev
heroku config:set SUPERUSER_NAME=xxx SUPERUSER_EMAIL=xxx SUPERUSER_PASSWORD SUPERUSER_API_TOKEN
git push heroku master
heroku run ./bin/superuser.sh
heroku run ./netbox/netbox/manage.py migrate
```

NOTE: This setup requires to use `git push` deploy always as submodule support is only enabled with git deployments.  https://devcenter.heroku.com/articles/git-submodules
