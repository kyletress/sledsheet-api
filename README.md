# Sledsheet API Documentation
## Authentication
Sledsheet is a read-only API. Authentication is not required. The URL is `http://www.sledsheet.com/api`. The API is undergoing active development and is subject to breaking changes. 

## API Endpoints
### GET /v1/athletes
Returns an array of all athletes

#### Parameters
* **q** *(optional)* - a search term to limit the returned results

#### Response
```json
[
  {
    "id":1,
    "name":"Kyle Tress"
  }
]
```

### GET /v1/athletes/:id
Returns the given athlete

#### Response
```.json
{
  "id":1,
  "name":"Kyle Tress",
  "country":"USA",
  "gender":"male"
}
```

### GET /v1/tracks
Returns an array of bobsled/skeleton tracks

#### Response
```.json
[
  {
    "id": 1,
    "name": "Altenberg"
  },
  {
    "id": 2,
    "name": "Calgary"
  }
]
```

### GET /v1/tracks/:id
Returns the given track

#### Response
```.json
{
  "id": 8,
  "name": "Lake Placid",
  "records": {
    "skeleton": {
      "men": {
        "start": {
          "time": 5450
        },
        "finish": {
          "time": 5450
        }
      },
      "women": {
        "start": {
          "time": 546
        },
        "finish": {
          "time": 5547
        }
      }
    }
  }
}
```

### GET /v1/timesheets
Returns an array of timesheets

#### Response
```.json
[
  {
    "id": 176,
    "name": "Winterberg World Cup Race 2015-16 Men"
  },
  {
    "id": 174,
    "name": "Altenberg World Cup Race 2015-16 Men"
  }
]
```

### GET /v1/timesheets/:id
Returns the given timesheet with an array of associated entries. TODO: Make entries and runs optional parameters. 

#### Response
```.json
{
  "id": 174,
  "name": "Altenberg World Cup Race 2015-16 Men",
  "date": "2015-11-28T00:00:00.000Z",
  "status": "complete",
  "entries": [
    {
      "id": 4251,
      "athlete": "Martins Dukurs",
      "total_time": 5660
    },
    {
      "id": 4252,
      "athlete": "Alexander Tretiakov",
      "total_time": 5663
    },
    {
      "id": 4253,
      "athlete": "Nikita Tregybov",
      "total_time": 5670
    }
  ]
}
```

### GET /v1/circuits
Return an array of all circuits

#### Response
```.json
[
  {
    "id":8,
    "name":"World Championship"
  },
  {
    "id":1,
    "name":"World Cup"
  }
]
```

### GET /v1/circuits/:id 
Returns the given circuit

#### Response
```.json
{
  "id":1,
  "name":"World Cup"
}
```

### GET /v1/seasons/:id
Returns an array of the given season's world rankings

#### Params
* **men** *(optional)* - Return an array of men's points
* **women** *(optional)* - Return an array of women's points

#### Response
```.json
[
  {
    "id": 5,
    "athlete": "Martins Dukurs",
    "world_rank": "1",
    "nation_rank": "LAT 1",
    "points": "675",
    "country": "LV"
  },
  {
    "id": 4,
    "athlete": "Alexander Tretiakov",
    "world_rank": "2",
    "nation_rank": "RUS 1",
    "points": "630",
    "country": "RU"
  }
]
```

### GET /v1/seasons/:id/athletes/:id
Return the given athlete and an array of their points for the given season

#### Response
```.json
{
  "id": 5,
  "name": "Martins Dukurs",
  "country": "LAT",
  "gender": "male",
  "total": 450,
  "points": [
    {
      "id": 176,
      "timesheet": "Winterberg WC",
      "value": 225
    },
    {
      "id": 174,
      "timesheet": "Altenberg WC",
      "value": 225
    }
  ]
}
```
