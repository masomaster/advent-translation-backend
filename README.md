# Advent Translation 2023

[Go to deployed version](https://www.adventtranslation.com/)

## About

This is a project, modeled after [Advent of Code](https://adventofcode.com/), providing 25 days of translation practice from Hebrew and Greek verses in the Bible for the Christmas/Advent 2023 season.

## Technologies

Kept it simple to get it off the ground asap:

- React
- MongoDB
- Node.js
- Express

Hosted on Vercel

## Getting Started

### Production
In order to work on Vercel without refactoring on deployment, `node server.js` or `npm run start` launch both the Express server and the react client. `npm run build` is required before deploying.

To do this, `package.json` includes these:
```
"main": "server.js",
  "scripts": {
    "build": "react-scripts build",
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js",
    "start-client": "react-scripts start",
    "start-server": "nodemon server.js"
  },
```
Be sure to remove  `"proxy": "http://localhost:3001"` from `package.json`


### Development
But for development, I want the React dev build available for easy updating, but then they run on different ports, so add this to `package.json`:
    `"proxy": "http://localhost:3001"`
Be sure to remove it when building and deploying. To run things for dev, run `npm run start-client` to start up the react dev environment, and `node server.js` to start up the Express server. The proxy will link them.

