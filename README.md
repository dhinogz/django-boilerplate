# Django Boilerplate

Simple Django boilerplate from William Vincent's Django for Professionals. 

Includes:
- Docker
- Allauth
- Bootstrap 4
- Crispy Forms

## Installation


First, clone repo
```bash
git clone https://github.com/dhinogz/django-boilerplate.git
```
Make sure you have Docker installed to create project container.

Then, run this command to install dependencies in container and run in Docker detach mode. 
```bash
docker-compose up -d --build
```
After first install, make migrations
```bash
docker-compose exec web python manage.py migrate
```

Run this command to shut down container
```bash
docker-compose down
```




## Usage

In order to use the command line on docker, use this code snippet at the start of every command
```bash
docker-compose exec web
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)