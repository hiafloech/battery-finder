# API Documentation

## Base URL
```
http://localhost:5000/api
```

## Endpoints

### Health Check
Check if the API is running.

**Request:**
```
GET /health
```

**Response:**
```json
{
  "status": "Backend is running!"
}
```

### Vehicles

#### Search Vehicles
Find vehicles by make, model, and year.

**Request:**
```
GET /vehicles?make=Toyota&model=Camry&year=2020
```

**Response:**
```json
[
  {
    "id": 1,
    "year": 2020,
    "make": "Toyota",
    "model": "Camry",
    "engine_type": "2.5L 4-cyl"
  }
]
```

### Batteries

#### Get Compatible Batteries
Get all batteries compatible with a specific vehicle.

**Request:**
```
GET /batteries/compatible/:vehicleId
```

**Response:**
```json
[
  {
    "id": 1,
    "name": "Car Battery Pro 12V",
    "voltage": 12,
    "capacity": 800,
    "cca": 600,
    "terminal_type": "top",
    "dimensions": "10.2 x 6.7 x 7.5",
    "price": 149.99
  }
]
```

### Retailers

#### Get Battery Availability
Find retailers with specific battery in stock.

**Request:**
```
GET /retailers/availability/:batteryId
```

**Response:**
```json
[
  {
    "retailer_id": 1,
    "retailer_name": "Auto Parts Plus",
    "stock_quantity": 5,
    "price": 149.99,
    "website": "www.autopartsplus.com",
    "phone": "1-800-123-4567"
  }
]
```

## Error Responses

All error responses follow this format:

```json
{
  "error": "Error message describing what went wrong"
}
```

### Status Codes
- `200` - OK
- `400` - Bad Request
- `404` - Not Found
- `500` - Internal Server Error

## Rate Limiting

Currently no rate limiting is implemented. This may be added in future versions.
