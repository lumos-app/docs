# Lumos Documentation

## macOS Server API

Port: 8082

### Test Connection

#### Request 

```
GET /api/v1/test
```

#### Response

- 200 bei Erfolg
- Timeout, wenn Server nicht gefunden wurde

### Images

#### Request

```
GET /api/v1/images
```

#### Response

```
{
    "success": true,
    "images": [
        {
            "uuid": "???",
            "filename": "???",
            "uploadedFrom": "???",
            "totalViewCount": 315,
            "show": true/false,
            "createdDate": "ISO8601",
            "data": "base64 encoded image (thumbnail) or empty string"
        }
    ]
}
```

### Upload Image

#### Request

```
POST /api/v1/images/upload
Content-Type: application/json

{
    "uuid": <generate uuid on device>,
    "name": <name from photographer>,
    "image": <base64 encoded jpeg image>
}
```

#### Response

- 200 bei Erfolg
- 400, 500 ?! Fehler
