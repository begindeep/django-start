# Dockerizing Django with Postgres, Gunicorn, Nginx and Certbot 

## 🚀 Features

### A Django stater project with fully basic requirements for a production-ready version.

1. Dockerizing Django with Postgres, Gunicorn, and Nginx.
	Refer: [django-on-docker](https://github.com/testdrivenio/django-on-docker)
2. Configuration for Nginx and Certbot with Let’s Encrypt on docker-compose.
	Refer: [nginx-certbot](https://github.com/wmnnd/nginx-certbot)
3. Django REST framework sample.
4. A batteries-included, opinionated template for Django.
	Refer: [djangox](https://github.com/wsvincent/djangox)
- User log in/out, sign up, password reset via [django-allauth](https://github.com/pennersr/django-allauth)
- Static files configured with [Whitenoise](http://whitenoise.evans.io/en/stable/index.html)
- Styling with [Bootstrap v4](https://github.com/twbs/bootstrap)
- Debugging with [django-debug-toolbar](https://github.com/jazzband/django-debug-toolbar)
- DRY forms with [django-crispy-forms](https://github.com/django-crispy-forms/django-crispy-forms)

### Development

Uses the default Django development server.

1. Rename *.env.dev-sample* to *.env.dev*.
2. Update the environment variables in the *docker-compose.yml* and *.env.dev* files.
3. Build the images and run the containers:

    ```sh
    $ docker-compose up -d --build
    ```

    Test it out at [http://localhost:8000](http://localhost:8000).

### Production

Uses gunicorn + nginx.

1. Rename *.env.prod-sample* to *.env.prod* and *.env.prod.db-sample* to *.env.prod.db*. Update the environment variables.
2. Build the images and run the containers:

    ```sh
    $ docker-compose -f docker-compose.prod.yml up -d --build
    ```

    Test it out at [http://localhost:1337](http://localhost:1337).
3. Modify init-letsencrypt.sh & app.conf with domains and email addresses and run it:
	```sh
    $ ./init-letsencrypt.sh
    ```
