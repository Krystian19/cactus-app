# Cactus app
Cactus app is an open source service to stream your favorite anime.

## Services
|  [Client Repo](https://github.com/Krystian19/cactus-app-client-service) | [Backend Repo](https://github.com/Krystian19/cactus-app-backend-service/tree/master) | [Admin Repo](https://github.com/Krystian19/cactus-app-backend-admin-service/tree/master) |
|:---------------------:|:---------------------:|:---------------------:|
| [![Build Status](https://travis-ci.org/Krystian19/cactus-app-client-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-client-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-client-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-client-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-client-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-client-service) | [![Build Status](https://travis-ci.org/Krystian19/cactus-app-backend-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-backend-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-backend-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-backend-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-backend-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-backend-service) | [![Build Status](https://travis-ci.org/Krystian19/cactus-app-backend-admin-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-backend-admin-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-backend-admin-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-backend-admin-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-backend-admin-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-backend-admin-service) |

|  [Image CDN Repo](https://github.com/Krystian19/cactus-fake-image-cdn-service/tree/master) | [Video CDN Repo](https://github.com/Krystian19/cactus-fake-video-cdn-service/tree/master) |
|:---------------------:|:---------------------:|
| [![Build Status](https://travis-ci.org/Krystian19/cactus-fake-image-cdn-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-fake-image-cdn-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-fake-image-cdn-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-fake-image-cdn-service)  [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-fake-image-cdn-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-fake-image-cdn-service) | [![Build Status](https://travis-ci.org/Krystian19/cactus-fake-video-cdn-service.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-fake-video-cdn-service) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-fake-video-cdn-service/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-fake-video-cdn-service) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-fake-video-cdn-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-fake-video-cdn-service) |

## Internal Libraries
|  [GraphQL Schema Module](https://github.com/Krystian19/cactus-app-schema-module/tree/master) | [JS DB module](https://github.com/Krystian19/cactus-app-db-module/tree/master)|
|:---------------------:|:---------------------:|
| [![Build Status](https://travis-ci.org/Krystian19/cactus-app-schema-module.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-schema-module) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-schema-module/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-schema-module) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-schema-module/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-schema-module)      | [![Build Status](https://travis-ci.org/Krystian19/cactus-app-db-module.svg?branch=master)](https://travis-ci.org/Krystian19/cactus-app-db-module) [![Code Climate](https://codeclimate.com/github/Krystian19/cactus-app-db-module/badges/gpa.svg)](https://codeclimate.com/github/Krystian19/cactus-app-db-module) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-db-module/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-db-module)

## Screenshots
![Alt text](screenshots/view1.png?raw=true "Anime Description view")

# Requirements

+ **Do you have Docker installed ?**
```sh
docker -v
  Docker version 18.03.0-ce # Or later
```

+ **Do you have git-lfs installed ?**
```sh
git-lfs --version
  git-lfs/2.5.2 (GitHub; darwin amd64; go 1.11) # Or later
```

# How to setup
Clone this project with all of it's modules recursively (it's a little heavy, so it'll take a bit):

```sh
git clone --recurse-submodules git@github.com:Krystian19/cactus-app.git
```

And start the project with:
```sh
docker-compose up -d
```

Then run the seeders to have some basic data ...
```sh
# Run the seeders
docker exec -ti cactus_backend_admin /code/seeds.sh
```

And voilà, the web client should be running @ http://localhost:5000/

## Todo list
+ - [ ] Work in the subtitles superposition in the video player
  + - [ ] Find a way of converting .ass files to .vtt
    + - [ ] Findout wether to do that conversion by hand or make it automated
+ - [ ] Study how generate captions based on a raw video file
+ - [ ] Implement HLS streaming for the video player view
+ - [ ] Setup TSlint for the client project
  + - [ ] Find a ts style guide to follow follow for the client project
+ - [ ] Setup Genre filtering in the client's search view
  + - [ ] Setup Genre filtering component
    + - [x] Setup pagination for the Genre schema resolver
    + - [x] Setup title filtering for the Genre schema resolver
    + - [x] Finish concept for the component
    + - [x] Setup markup for the filtering component
    + - [ ] Setting up genre filtering through the a URL param or state
+ - [ ] Setup a way in the anime info view to connect with the next season
+ - [ ] Find a practical way of generating captions for raw videos
+ - [x] Find a better design for the video player
  + - [ ] Implement the better design for the video player component
+ - [ ] Implement a not found page for content that is not found
  + - [ ] Setup component to be used in such cases
+ - [ ] Create an error component to show if the client's requests fails
  + - [ ] Create a method of handling request failures that can be used universally between components.
+ - [ ] Add more series to the backend-admin's seeding script data
+ - [ ] Setup multi-language support for the client
+ - [ ] Complete missing tests of backend admin's models
+ - [ ] Complete model tests for the db module
+ - [ ] Study how to convert the Frontend app in a Desktop native app
  + - [ ] Study how to distribute updates to said Desktop app

## License
MIT © [Jan Guzman](https://github.com/Krystian19)
