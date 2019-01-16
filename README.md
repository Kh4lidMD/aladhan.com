## بِسْمِ اللهِ الرَّحْمٰنِ الرَّحِيْمِ

# Al Adhan App

This is the code you see deployed on https://aladhan.com. This documentation explains how you can get setup
to deploy your own instance and contribute code.

## Technology Stack and Requirements
* PHP 7.2
* Composer - See composer.json for other dependencies
* Slim Framework
* Bootstrap 3
* JQuery
* Bootstrap Multiselect
* Media Elements JS
* Docker

## Getting Started

### Running the App

The app is fully Dockerised. You **just need docker** to spin it up.

A production ready Docker image of the app is published as vesica/aladhan.com on Docker Hub (https://hub.docker.com/r/vesica/aladhan.com/).

To get your own instance up, simply run:

```
docker run -it -p 8082:8080  vesica/aladhan.com:latest
``` 

You can now visit http://localhost:8082/ and start using it.

### Build and Contribute

In the mean time:

1. Clone this repository
2. Run ```docker build . -t vesica/aladhan.com```. This will build an image with production dependencies only.
3. Run ```docker run -it -p 8081:8080  -v ($pwd)/.:/var/www vesica/aladhan.com``` to spin up the built image.
3. Run ```composer install``` to add development dependencies.
6. Make sure you have internet connectivity so the app can connect to https://api.aladhan.com.
7. Open your browser and browse to http://localhost:8081/.
8. Any changes you make will be synced to the Docker container. You just refresh the page in the browser to see them.

## Scaling and Sizing

This app takes 16-17 MB per apache process / worker and is set to have a maximum of 29 Apache workers.

A single instance should be sized with a maximum of 704 MB RAM, after which you should scale it horizontally.

## Contributing Code

You can contribute code by raising a pull request.

There's a backlog of stuff under issues for things that potentially need to be worked on, so please feel free to pick something up from there or contribute your own improvements.
