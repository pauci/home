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
    "addr": "1a2b3c4d5e",
    "sensors": [
    	{
    	    "id": "1",
    	    "type": "DHT22",
    	    "values": {
    	        "h": "humidity [%]",
    	        "t": "temperature [C]"
	    },
	    "status": "ready"
    	},
    	{
    	    "id": "bmp1",
    	    "type": "BMP180",
    	    "values": {
    	       "p": "barometric pressure [hPa]",
    	       "t": "temperature [C]",
    	       "a": "altitude [m]"
    	    },
    	    "status": "disconnected"
    	}
    ]
}
```

```
GET /devices/{addr}/sensors/{id}
```

```json
{
    "status": "OK",
    "values": {
        "h": "55.4%",
        "t": "21.2C"
    }
}
```
