# General Intro
## The idea

* We crunch through property rentalpricing and their locations
* and return property location and property price
* and generate a heatmap that shows how expensive property depending on location in Bangkok.
* we will have several sets of pricing sets, like:
  * low: 2500, median: 5000, high: 7500
  * low: 7500, median: 10000, high 12500
  * etc.
* also we will have general price overview (from 0 to 200000) in Bangkok

## Bonus functionality

* have highlighted BTS/MRT lines 
* have a heatmap for property sale pricing
* display property density with a color intensity
* Those data posted to the blog, have links to our main site.
* So they generate leads to our main site.

## Technologies

* [javascript](https://www.javascript.com/)
* [google maps](https://www.google.com/maps)

# Frontend
## Intro

* we use google maps to draw heatmap
* we consume data from the backend through API
* request to backend API has coordinates for window that we want to show to user
* also request to backend contains how much points it wants

## Color scheme

* Blue color code low price
* Green color code median price
* Red color

## Technologies

* [Node.js](https://nodejs.org/en/)
* [Express.js](http://expressjs.com/)
* [Jade](https://github.com/pugjs/pug)
* [Jade bootstrap](http://rajasegar.github.io/JADE-Bootstrap/getting-started.html)

# Backend
## Intro

* backend provide API for the frontend
* backend get geodata from PG DBs
* backend cluster data according to amount of points requested from frontend
* and return a [WeightedLocationSet][WeightedLocationSet], for example:

```json
[
    {
        "location": {
            "latitude": 13.7251097,
            "longitude": 100.3529055,
        },
        "weight": 0.5
    },
    {
        "location": {
            "latitude": 14.7251097,
            "longitude": 99.3529055,
        },
        "weight": 1
    }
]
```

# How to use
## Installation

```
git@bitbucket.org:krizalys/property-price-heatmap.git
brew install node
npm install
```

## Start

```
npm start
```

Then open `localhost:8000` in browser.

[WeightedLocationSet]: https://bitbucket.org/krizalys/property-price-heatmap/src/master/schema/json/WeightedLocationSet.json?fileviewer=file-view-default
