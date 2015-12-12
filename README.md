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
  "athlete":
    {
      "id":1,
      "name":"Kyle Tress",
      "country":"USA",
      "gender":"male"
    }
}
```

### GET /v1/tracks
Returns an array of bobsled/skeleton tracks

#### Response
```.json
[
  {
    "id":1,
    "name":"Altenberg"
  },
  {
    "id":2,
    "name":"Calgary"
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
