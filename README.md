# Django Boilerplate

Simple Django boilerplate from William Vincent's Django for Professionals. 

Includes:
- Docker 
- Built in user management with allauth (also includes custom allauth templates)
- Base template with simple navbar and home/about templates
- Custom User Model set up
- Finished tests for accounts and pages app
- Page app includes Home and About views
- Responsive CSS styling with Bootstrap 4
- Crispy Forms

## Installation

### Initial
First, clone repo
```bash
$ git clone https://github.com/dhinogz/django-boilerplate.git
```

Change name and enter directory
```bash
$ mv django-boilerplate project_name && cd project_name
```
### Environment variables
We're gonna want to create a .env.dev file to store our environment variables
```bash
$ touch .env.dev
```

We're gonna need to generate a SECRET_KEY to paste into our .env.dev file. To do so, run following code on the command line.
```bash
$ python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())'
```
Example output:
```
2x$e%!k_u_0*gq0s4!_u(2(^lpy&gir0hg)q&5nurj0-sseuav
```

Add following text to .env.dev file:
```
DEBUG=1
SECRET_KEY= OUR GENERATED SECRET KEY
DJANGO_ALLOWED_HOSTS=localhost 127.0.0.1 [::1]
```

### Docker
Make sure you have Docker and docker-compose installed to build project container.

Then, run this command to install dependencies in container and run in Docker detach mode. 
```bash
$ docker-compose up -d --build
```
After first install, make migrations
```bash
$ docker-compose exec web python manage.py migrate
```

Run this command to shut down container
```bash
$ docker-compose down
```

## Usage

In order to use the command line on docker, use this code snippet at the start of every command
```bash
$ docker-compose exec web
```

For example, let's suppose we want to start an app in our Docker instance. We would run the following code:
```bash
$ docker-compose exec web python manage.py startapp app_name
```

### Static files in production
Before deploying, we need to run collectstatic to create a single, production-ready directory of all the static files in our project.
```bash
$ docker-compose exec web python manage.py collectstatic
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)