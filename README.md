# Cactus app
Cactus app is an open source service to stream your favorite anime.

## Service Repositories
|  [Backend Repo](https://github.com/Krystian19/cactus-app-backend-service/tree/master) | [Backend Admin Repo](https://github.com/Krystian19/cactus-app-backend-admin-service/tree/master) | [Video CDN Repo](https://github.com/Krystian19/cactus-fake-video-cdn-service/tree/master) |
|:---------------------:|:---------------------:|:---------------------:|
| [![Build Status](https://travis-ci.org/Krystian19/cactus-app-backend-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-backend-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-backend-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-backend-service)       | [![Build Status](https://travis-ci.org/Krystian19/cactus-app-backend-admin-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-backend-admin-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-backend-admin-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-backend-admin-service)  | [![Build Status](https://travis-ci.org/Krystian19/cactus-fake-video-cdn-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-fake-video-cdn-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-fake-video-cdn-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-fake-video-cdn-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-fake-video-cdn-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-fake-video-cdn-service) |

|  [Image CDN Repo](https://github.com/Krystian19/cactus-fake-image-cdn-service/tree/master) |
|:---------------------:|
| [![Build Status](https://travis-ci.org/Krystian19/cactus-fake-image-cdn-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-fake-image-cdn-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-fake-image-cdn-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-fake-image-cdn-service)  
[![Test Coverage](https://codecov.io/gh/Krystian19/cactus-fake-image-cdn-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-fake-image-cdn-service)     |

## Screenshots
![Alt text](screenshots/view1.png?raw=true "Anime Description")

# Setup

Clone this project with all of it's modules recursively:

```sh
git clone --recurse-submodules git@github.com:Krystian19/cactus-app.git
```

And start the project with:
```sh
docker-compose up -d
```

Run the seeders ...

NOTE: Where "cactus-app_backend_admin_1" is the fullname of the running backend container, it might change in newer versions of docker, so do a "docker ps" to find out the fullname of the running backend_admin container.
```sh
# Run the seeders
docker exec -ti cactus-app_backend_admin_1 /code/seeds.sh
```

The web client should be running @ http://localhost:5000/

## Todo list
+ - [ ] Add more series to the backend-admin's seeding script data
+ - [x] Setup a more stable process of Anime, Episode and Season creation in the backend_admin (currently unstable and volatile)
+ - [x] Setup backend service testing pipeline, maintainability score
    - [x] Write tests for this service
        - [x] Write instructions of how to run the tests
    - [x] Write travis configfile for this module
    - [x] Setup db module testing pipeline, maintainability score
        - [ ] Write seeder script for this module
        - [x] Write tests for this module
            - [x] Write instructions of how to run the tests
        - [x] Write travis configfile for this module
    - [x] Setup schema module testing pipeline, maintainability score
        - [x] Write tests for this module
        - [x] Write travis configfile for this module
+ - [x] Setup backend_admin service testing pipeline, maintainability score
    - [x] Write tests for this service
        - [x] Write instructions of how to run the tests
    - [x] Write travis configfile for this module
    - [x] Write seeder script for this module
+ - [ ] Setup client service testing pipeline, maintainability score
    - [ ] Write tests for this service
        - [ ] Write instructions of how to run the tests
    - [ ] Write travis configfile for this module


<!-- - [x] Venus -->

## License
MIT © [Jan Guzman](https://github.com/Krystian19)
