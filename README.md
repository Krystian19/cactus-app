# Cactus app 

Cactus app is a demonstration service to stream your favorite anime. Built in mostly Go and TypeScript.

## Services
|  [Client Repo](https://github.com/Krystian19/cactus-app-client-service) | [BFF Repo](https://github.com/Krystian19/cactus-app-bff-service/tree/master) | [Core Repo](https://github.com/Krystian19/cactus-app-core-service/tree/master) |
|:---------------------:|:---------------------:|:---------------------:|
| [![Codacy Badge](https://app.codacy.com/project/badge/Grade/13cae8df73d54af1b59af877141de2f6)](https://www.codacy.com/gh/Krystian19/cactus-app-client-service/dashboard?utm_source=github.com&utm_medium=referral&utm_content=Krystian19/cactus-app-client-service&utm_campaign=Badge_Grade) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-client-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-client-service) | [![Codacy Badge](https://app.codacy.com/project/badge/Grade/119a96c518a04cf4812174a4962d6628)](https://www.codacy.com/gh/Krystian19/cactus-app-bff-service/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Krystian19/cactus-app-bff-service&amp;utm_campaign=Badge_Grade) | [![Codacy Badge](https://app.codacy.com/project/badge/Grade/108d242cd8da436c8634c1760859fa1d)](https://www.codacy.com/gh/Krystian19/cactus-app-core-service/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Krystian19/cactus-app-core-service&amp;utm_campaign=Badge_Grade) |

|  [Admin Repo](https://github.com/Krystian19/cactus-app-admin-service/tree/master) | 
|:---------------------:|
| [![Codacy Badge](https://app.codacy.com/project/badge/Grade/16b9691b8c4b45bb82e592b7af6e1d7d)](https://www.codacy.com/gh/Krystian19/cactus-app-admin-service/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Krystian19/cactus-app-admin-service&amp;utm_campaign=Badge_Grade) [![Test Coverage](https://codecov.io/gh/Krystian19/cactus-app-admin-service/branch/master/graph/badge.svg)](https://codecov.io/gh/Krystian19/cactus-app-admin-service)

## Internal Tools & Libraries
|  [Video editing tool](https://github.com/Krystian19/cactus-app-video-editing-tool)
|:---------------------:|
| [![Codacy Badge](https://app.codacy.com/project/badge/Grade/633ecb0f303e4103a6cadd264d4042d4)](https://www.codacy.com/gh/Krystian19/cactus-app-video-editing-tool/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Krystian19/cactus-app-video-editing-tool&amp;utm_campaign=Badge_Grade)

## Screenshots
![Alt text](screenshots/capture1.png?raw=true "Anime Description view")

# Requirements

+ **Do you have Docker installed ?**
```sh
docker -v
  Docker version 20.10.2 # Or later
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

Export your credentials on your PATH:
```sh
# You will get your access token here https://github.com/settings/tokens (with access to private repos permission)
export ACCESS_TOKEN_USR=YOUR_GITHUB_USER
export ACCESS_TOKEN_PWD=GITHUB_ACCESS_TOKEN
```

Build your images:
```sh
docker-compose build --build-arg ACCESS_TOKEN_USR=${ACCESS_TOKEN_USR} --build-arg ACCESS_TOKEN_PWD=${ACCESS_TOKEN_PWD}
```

And start the project with:
```sh
docker-compose up -d
```

Then run the seeders to have some basic data ...
```sh
# Run the seeders
docker exec -ti cactus_admin /code/seeds.sh
```

And voilà, the web client should be running @ http://localhost:5000/

## Todos
+ - [x] Enforce function return type on the client's code
+ - [x] Improve shell script on the wait.sh in the client's CI pipeline, to avoid waiting forever for the build to finalize.
+ - [ ] Setup an Object generator for the types used in the testing files https://medium.com/@jaferson123/tdd-factory-generator-with-factory-ts-and-faker-js-to-ease-your-testing-in-typescript-applications-5afdd45e6e8
  + - [ ] Avoid cyclic releations on data
+ - [x] Replace query strings with multiline strings in the core service to make the queries more readable.
+ - [x] Inside of the query strings in the core service, use the table name coming from the model functions instead of hardcoding them.
+ - [ ] Remove test.jpg and test.mp4 from lfs to ensure that when the projects are cloned without lfs, those files are always present.
+ - [ ] Take into account that with the new changes, Movies/Specials will appear on the Hottest/Newest Episodes section (in the title it should show that it is a movie or an special)
+ - [ ] In the Anime Search view thumbnails show the name of the anime and the season, (Not the seasons's name)
+ - [ ] Make Release titles optional, if the Relaese title of a Season is not specified mark it as "title (Season 1)", if it's not a Season then just display the Anime name.
+ - [ ] Setup client support for movies, ovas and specials
    + - [ ] Setup client's Anime Details view to support Movies
+ - [ ] Setup Multi-language support for Episodes, Movies, and OVAs (Including Markup)
+ - [ ] Setup schedule view support for episodes that are out but not translated
+ - [ ] Setup schedule view support for delayed episodes
  + - [ ] Set time countdown for an episode in the anime info view (state delayed episodes)
  + - [ ] Episodes can be delayed for more than 2 weeks find a way of showing that.
+ - [ ] Setup session based security in the client service to provent access to the static files if the client is lacking the session value
+ - [ ] Limit the amount of categories that can be filtered (to 4) (Check for the compatibility in mobile, it breaks when there's a lot of them)
+ - [x] Improve client's support for mobile
  + - [x] Scrolling is painfully slow in IOS devices
+ - [ ] Setup Google Analytics support throughout the app
  + - [ ] Setup base Google Analytics snippet to check the amount of people in the app right now
  + - [ ] Setup base Google Analytics snippet to check the amount of people in an specific episode
    + - [ ] Setup DB support to save Google Analytics snippets to be rendered on every episode of any series.
+ - [ ] Create an infraestructure repo for the cactus project
+ - [ ] Setup multi-language support for the app
  + - [x] Setup a way of signaling that an episode is only available in a certain language
  + - [x] Caption support for the video player, video server and backend admin
  + - [ ] Setup Category title support based in the language
+ - [ ] Setup Multi-language support for categories
    + - [ ] Setup Multi-language display for categories
        + - [ ] Setup Multi-language search for categories
+ - [ ] Implement HLS streaming for the video player view
  + - [x] Study how to implement HLS properly
  + - [x] Implement a proper HLS Video player
  + - [x] Implement a proper local HLS server for development
  + - [ ] Set video server to serve static subtitle files
    + - [ ] Setup a proper styling for those subtitles
+ - [ ] Setup the django admin to leverage massive anime content amounts
+ - [ ] Setup a way in the anime info view to connect with the next season
+ - [x] Setup db support for movies and ovas
+ - [ ] Setup support for episodes that are not available in the user's browser language
    + - [ ] Setup support for raw episodes and movies client-side
+ - [x] Setup views tracking of the anime video view
+ - [ ] Setup SEO support for the whole application
  + - [ ] Setup SEO support for every anime episode detail view
+ - [x] Add picture-in-picture functionality to the video player
+ - [ ] Define a proper pipeline that edits videos programmatically
  + - [x] Develop cli to interact with video editing pipeline
  + - [x] Apply steps of the process programmatically
  + - [ ] Setup cactus intro video sequence for edited videos
  + - [ ] Include subtitle time editing (modify subtitle appearance times)
  + - [ ] Setup proper cactus watermark
  + - [ ] Setup proper cactus intro sequence in the edited videos
+ - [ ] Implement a not found page for content that is not found
  + - [ ] Setup component to be used in such cases
+ - [ ] Create an error component to show if the client's requests fails
  + - [ ] Create a method of handling request failures that can be used universally between components.
+ - [ ] Add more series to the backend-admin's seeding script data
+ - [ ] Complete missing tests of backend admin's models

## License
© [Jan Guzman](https://github.com/Krystian19)
