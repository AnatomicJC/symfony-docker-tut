# How-to-use

Clone repository and go inside it:

```
git clone git@github.com:AnatomicJC/symfony-docker-tut.git
cd symfony-docker-tut
```

Create `app` directory (this will host your code):

```
mkdir app
```

Launch the docker stack (we use UID/GID to be able to edit code from your computer):

```
UID=${UID} GID=${GID} docker compose up --build
```

To create a new Symfony app, jump into the php container:

```
UID=${UID} GID=${GID} docker-compose exec php /bin/bash
```

From there, launch the `symfony new .` command:

```
I have no name!@a9001fa29b8b:/var/www/symfony_docker$ symfony new .
* Creating a new Symfony project with Composer
  (running /usr/local/bin/composer create-project symfony/skeleton /var/www/symfony_docker  --no-interaction)

* Setting up the project under Git version control
  (running git init /var/www/symfony_docker)


 [OK] Your project is now ready in /var/www/symfony_docker

```

You can visit your newly created Symfony website on [http://localhost:8080/](http://localhost:8080/).

To clean everything, run the `docker-compose down -v` and `rm -rf app`.

Please enjoy!
