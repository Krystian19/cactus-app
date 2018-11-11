# Cactus app
Cactus app project repo.

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
- [ ] Create a fake CDN Image Service. (emulate a remote cdn with a local service).
    - [ ] Install cdn service for client's app consumption
- [ ] Create a fake Video Host Service. (emulate a remote video host with a local service).
    - [ ] Include a Reactjs based video player in the client app.
- [ ] Create a service to manage the content on the app, and db migrations. (preferably a django app).
<!-- - [x] Venus -->

## License
MIT © [Jan Guzman](https://github.com/Krystian19)
