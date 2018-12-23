# Cactus app
Cactus app is an open source service to stream your favorite anime.

# Requirements
```sh
docker -v
  Docker version 18.03.0-ce # Or later

git-lfs --version
  git-lfs/2.5.2 (GitHub; darwin amd64; go 1.11) # Or later
```

## Services
|  [Backend Repo](https://github.com/Krystian19/cactus-app-backend-service/tree/master) | [Admin Repo](https://github.com/Krystian19/cactus-app-backend-admin-service/tree/master) | [Video CDN Repo](https://github.com/Krystian19/cactus-fake-video-cdn-service/tree/master) |
|:---------------------:|:---------------------:|:---------------------:|
| [![Build Status](https://travis-ci.org/Krystian19/cactus-app-backend-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-backend-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-backend-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-backend-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-backend-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-backend-service)      | [![Build Status](https://travis-ci.org/Krystian19/cactus-app-backend-admin-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-backend-admin-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-backend-admin-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-backend-admin-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-backend-admin-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-backend-admin-service)  | [![Build Status](https://travis-ci.org/Krystian19/cactus-fake-video-cdn-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-fake-video-cdn-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-fake-video-cdn-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-fake-video-cdn-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-fake-video-cdn-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-fake-video-cdn-service) |

|  [Image CDN Repo](https://github.com/Krystian19/cactus-fake-image-cdn-service/tree/master) |
|:---------------------:|
| [![Build Status](https://travis-ci.org/Krystian19/cactus-fake-image-cdn-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-fake-image-cdn-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-fake-image-cdn-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-fake-image-cdn-service)  [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-fake-image-cdn-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-fake-image-cdn-service)|

## Screenshots
![Alt text](screenshots/view1.png?raw=true "Anime Description")

# How to Setup

Clone this project with all of it's modules recursively:

```sh
git clone --recurse-submodules git@github.com:Krystian19/cactus-app.git
```

And start the project with:
```sh
docker-compose up -d
```

Then you run the seeders ...

**NOTE:** Where **"cactus_app_backend_admin"** is the name of the backend_admin container, it might change in newer versions of docker, so do a **"docker ps"** to get the fullname of the running backend_admin container.
```sh
# Run the seeders
docker exec -ti cactus_app_backend_admin /code/seeds.sh
```

The web client should be running @ http://localhost:5000/

## Todo list
+ - [x] Set db's default collation to universal_ci (comes in swedish by default)
+ - [x] Setup a proper lazy loading mechanism for images in the client
+ - [x] Work with the LazyLoading image error placeholder
+ - [x] Set a default image value for all the image related fields
+ - [ ] Find and implement a better design for the current video player component
+ - [x] (Model Change): Episode title's text and language should be part of the episode version not in a separate model.
+ - [x] Set up the broadcast day/time for the Anime Seasons
  + - [x] Seed Seasons with the proper day/time values
+ - [ ] Move error image placeholder and missing images placeholders to the client's server
+ - [ ] Fix the sidebar's component replication problem
+ - [ ] Setup the client's schedule view
  + - [ ] Implement each Season's airing time and calculate the remaining time
  + - [x] Create WeekDay model in the backend and backend-admin services
  + - [x] Include WeekDay as a Schema query method
  + - [x] Implement proper query request and information usage in the client's schedule view
+ - [ ] Add more series to the backend-admin's seeding script data
+ - [ ] Setup client service testing pipeline, maintainability score
    - [ ] Write tests for this service
        - [ ] Write instructions of how to run the tests
    - [ ] Write travis configfile for this module
+ - [ ] Create an error component to show if the client's requests fails
+ - [x] Fill in missing types from the Schema tests (WeekDay model not being tested)
+ - [ ] Complete missing tests of backend admin's models
+ - [ ] Complete model tests for the db module


<!-- - [x] Venus -->

## License
MIT © [Jan Guzman](https://github.com/Krystian19)
