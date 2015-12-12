# Sledsheet API Documentation
## Authentication
Sledsheet is a read-only API. Authentication is not required. The URL is `http://www.sledsheet.com/api`. The API is undergoing active development and is subject to breaking changes. 

## API Endpoints
### GET /v1/athletes
Returns an array of all athletes

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
