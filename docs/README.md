# Indexr

Automated dashboard creation using Docker labels. Designed for use with Docker Compose. Mostly proof of concept right now, so things may be funky.

![Preview](preview.png)

Features:
- Automatic service list
- Random Unsplashed background picture

## Use

Label your containers with each of the following:

| Label           	| Purpose                                             	|
|-----------------	|-----------------------------------------------------	|
| `indexr.enable` 	| Whether the service will be added to the dashboard  	|
| `indexr.name`   	| The name the service will have on the dashboard     	|
| `indexr.url`    	| The URL the service link will lead to               	|
| `indexr.icon`   	| The icon of the service (must be in `static/icons`) 	|

If any of the labels are missing, the service will not appear on the dashboard

## Development server

Set `FLASK_APP` to `indexr.py` and run `flask run`.

## Docker

There is a development Dockerfile provided, which uses the built-in Flask server: `docker run --name indexr -d -p 80:80 -v /var/run/docker.sock:/var/run/docker.sock:ro duhio/indexr:latest`
