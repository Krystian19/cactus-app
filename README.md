# Cactus app
Cactus app project repo.

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

## Todo list
- [ ] Setup backend service testing pipeline, maintainability score, and code coverage
    - [ ] Write tests for this service
    - [ ] Write travisci configfile for this module
    - [ ] Setup db module testing pipeline, maintainability score, and code coverage
        - [ ] Write seeder script for this module
        - [ ] Write tests for this module
        - [ ] Write travisci configfile for this module
    - [ ] Setup schema module testing pipeline, maintainability score, and code coverage
        - [ ] Write tests for this module
        - [ ] Write travisci configfile for this module
- [ ] Setup backend_admin service testing pipeline, maintainability score, and code coverage
    - [ ] Write tests for this service
    - [ ] Write travisci configfile for this module
- [ ] Setup client service testing pipeline, maintainability score, and code coverage
    - [ ] Write tests for this service
    - [ ] Write travisci configfile for this module


<!-- - [x] Venus -->

## License
MIT © [Jan Guzman](https://github.com/Krystian19)
