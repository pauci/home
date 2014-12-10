iHome
====

## Infrastructure

Devices and sensors <-> Device hub/Ethernet Gateway <-> PC/Server <-> Clients (browsers, mobile apps)

## Hub API

```
GET /devices/{addr}
```

```json
{
    "addr": 0x1234ab,
    "sensors": [
    	{
    	    "id": "t",
    	    "type": "temperature",
    	    "unit": "C"
    	},
    	{
    	    "id": "h",
    	    "type": "humidity",
    	    "unit": "%"
    	}
    ]
}
```

```
GET /devices/{addr}/sensors/{id}
```

```json
{
    "value": 19.5,
    "unit": "C"
}
```
