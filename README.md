![Alt text](http://gioco.pro/wp-content/uploads/2014/09/logo_small2.png "A gamification API Gioco Pro")

# Gioco Pro API Docs
Gioco Pro API Docs are related to [Gioco Pro service](http://www.gioco.pro)
A easy way to implement gamification based on plug and play concept. Doesn't matter if you already have a full and functional database, Gioco will smoothly integrate everything and provide all methods and analytics that you might need.

# Usage

**Every request made to Gioco API's must include a custom header token wiht the Application Token.**

## Resource

### Get User data
GET - **Get Resource** *(aid: ```Integer```)*

*aid parameter is resource unique id into your application.*

Examples:

```shell
curl --header "token: YOUR TOKEN HERE" -X GET -d resource="{aid:USER ID HERE}" \ https://app.gioco.pro/api/get_resource.json
```

## Events

### Tracking Events
POST - **Track Event** *(name: ```String```, aid: ```Integer```)*

- **name** parameter is the name of the event.
- **aid** parameter is resource unique id into your application.

Examples:

```shell
curl --header "token: YOUR TOKEN HERE" -X POST -d 'event={name:"EVENT NAME HERE"}' -d 'resource={aid:USER ID HERE}' \ http://app.gioco.pro/api/track_event.json
```

## Ranking

### Retrieve Ranking
Get - **Retrieve Ranking** *(size: ```Integer```, batch: ```Integer```)*

- **size** (the max number is 100) parameter is the number of resources that will be returned per batch.
- **batch** is the batch of the ranking you want to return, it is intended to paginate the ranking.

Examples:

```shell
curl --header "token: YOUR TOKEN HERE" -X GET -d size="SIZE HERE" -d batch="BATCH HERE" https://app.gioco.pro/api/ranking/retrieve.json
```
