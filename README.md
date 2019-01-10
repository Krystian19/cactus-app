# Cactus app
Cactus app is an open source service to stream your favorite anime.

# What do you need to have installed ?
```sh
docker -v
  Docker version 18.03.0-ce # Or later

git-lfs --version
  git-lfs/2.5.2 (GitHub; darwin amd64; go 1.11) # Or later
```

## Service Repostories
|  [Client Repo](https://github.com/Krystian19/cactus-app-client-service) | [Backend Repo](https://github.com/Krystian19/cactus-app-backend-service/tree/master) | [Admin Repo](https://github.com/Krystian19/cactus-app-backend-admin-service/tree/master) |
|:---------------------:|:---------------------:|:---------------------:|
| [![Build Status](https://travis-ci.org/Krystian19/cactus-app-client-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-client-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-client-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-client-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-client-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-client-service) | [![Build Status](https://travis-ci.org/Krystian19/cactus-app-backend-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-backend-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-backend-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-backend-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-backend-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-backend-service) | [![Build Status](https://travis-ci.org/Krystian19/cactus-app-backend-admin-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-backend-admin-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-backend-admin-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-backend-admin-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-backend-admin-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-backend-admin-service) |

|  [Image CDN Repo](https://github.com/Krystian19/cactus-fake-image-cdn-service/tree/master) | [Video CDN Repo](https://github.com/Krystian19/cactus-fake-video-cdn-service/tree/master) |
|:---------------------:|:---------------------:|
| [![Build Status](https://travis-ci.org/Krystian19/cactus-fake-image-cdn-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-fake-image-cdn-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-fake-image-cdn-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-fake-image-cdn-service)  [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-fake-image-cdn-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-fake-image-cdn-service) | [![Build Status](https://travis-ci.org/Krystian19/cactus-fake-video-cdn-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-fake-video-cdn-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-fake-video-cdn-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-fake-video-cdn-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-fake-video-cdn-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-fake-video-cdn-service) |

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
```sh
# Run the seeders
docker exec -ti cactus_app_backend_admin /code/seeds.sh
```

And voilà, the web client should be running @ http://localhost:5000/

## Todo list
+ - [ ] The stoppedAiring field in the DB module should be a boolean not a date.
+ - [ ] Find and implement a better design for the current video player component
+ - [ ] Move error image placeholder and missing images placeholders to the client's server
+ - [ ] Setup a default a proper default image when no poster and/or background are defined for a Season
+ - [ ] Fix the sidebar's component replication problem
+ - [ ] Implement a not found page for for requests outside of client or content that is not found
+ - [ ] Add more series to the backend-admin's seeding script data
+ - [ ] Create an error component to show if the client's requests fails
+ - [ ] Setup Category filters for the search view
  + - [ ] Implement Category filtering Component for the search view
  + - [ ] Implement Category filtering in the findSeason and the countSeasons query methods
    + - [ ] Include the category filtering in the findSeason and the countSeasons query methods unit tests
+ - [ ] Complete missing tests of backend admin's models
+ - [ ] Complete model tests for the db module


<!-- - [x] Venus -->

## License
MIT © [Jan Guzman](https://github.com/Krystian19)
