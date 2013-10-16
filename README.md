Home
====

Home API
--------

## 1. Discover devices #

### 1.1 Description #


### 1.2 Request #
```
/api/discover
```

### 1.3 Request example #
```json
{
	"onlyNew": false,
	"categories": ["inputs", "outputs"],
	"types": ["button", "switch", "rotary", "motion", "temperature", "humidity", "light", "display"]
}
```


### 1.4 Response #

Contains list of discovered devices

### 1.5 Response example #
```json
{
	"inputs": [
		{
			"addr": 101,
			"type": "button"
		},
		{
			"addr": 102,
			"type": "switch"
		},
		{
			"addr": 103,
			"type": "rotary",
			"range": 255
		},
		{
			"addr": 104,
			"type": "motion"
		},
		{
			"addr": 105,
			"type": "temperature"
		},
		{
			"addr": 106,
			"type": "humidity"
		}
	],
	"outputs": [
		{
			"addr": 201,
			"type": "light",
			"dimmable": true,
			"chromatic": true
		},
		{
			"addr": 202,
			"type": "light",
			"count": 500,
			"dimmable": true,
			"chromatic": true
		},
		{
			"addr": 203,
			"type": "display"
		}
	]
}
```


