
Setup
```
brew install node
npm install -g backstopjs #https://github.com/garris/BackstopJS#installation
backstop init #creates the backstop.json and backstop_data/*
#Change the page under test inside backstop.js (scenarios.0.url) to be http://host.docker.internal/login
```
Run
```
vendor/bin/sail up -d #Turn on the project
backstop test --docker #The actual test
backstop approve #If the test found differences, but you say "yeah, that's what I wanted to change"
```
