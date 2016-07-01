# paid
Python App In a Docker (PAID) example prepared for Moscow [Python Meetup](http://www.moscowpython.ru/meetup/35/dokerizacija-prilozhenij-na-python/) and Pycon Russia 2016.

## Prepare
First you should provision a Docker host (e.g. with [Docker Machine](https://docs.docker.com/machine/)) and install [Docker Compose](https://docs.docker.com/compose/).

## Get an image
Clone this repo
```bash
git clone git@github.com:satyrius/paid.git && paid
```
Build an image
```bash
docker-compose build
```
## Up and run
Start containers with compose
```bash
docker-compose up -d
```
Run Django migrations
```
docker exec web /opt/demo/app/manage.py migrate --no-input
```
You can create a user
```bash
docker exec -it web /opt/demo/app/manage.py createsuperuser
```
And check how it works in browser
```
http://<docker_host_ip>/admin/
```
