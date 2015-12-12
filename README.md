# Sledsheet API Documentation
## Authentication
Sledsheet is a read-only API. Authentication is not required. The URL is `http://www.sledsheet.com/api`.

## API Endpoints
### GET /v1/athletes.json
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

### GET /v1/athletes/:id.json
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

