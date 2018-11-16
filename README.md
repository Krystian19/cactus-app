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

- [x] Setup the eslint line length max of 80 on all js-centric services and submodules.
- [x] Setup client's app to consume the local image cdn.
    - [x] Create a fake CDN Image Service. (emulate a remote cdn with a local service).
- [x] Include a Reactjs based video player in the client app.
    - [x] Create a fake Video Host Service. (emulate a remote video host with a local service).
- [x] Create a service to manage the content on the app, and db migrations. (preferably a django app).
    - [x] Replicate sequelize's models into the backend admin app
    - [x] Write db migrations for the current models
    - [x] Expose relevant models to the Django Admin profile
    - [ ] Write seeders for all the Django Admin models

<!-- - [x] Venus -->

## License
MIT © [Jan Guzman](https://github.com/Krystian19)
