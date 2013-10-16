Home
====

## 1. Home API

### 1.1. Device discovery

#### 1.1.1. Description

#### 1.1.2. Request
```
/api/discover
```

```json
{
	"onlyNew": false,
	"categories": ["inputs", "outputs"],
	"types": ["button", "switch", "rotary", "motion", "temperature", "humidity", "light", "display"]
}
```

#### 1.1.3. Response

List of discovered devices

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

### 1.2. Write to device

/api/set/<addr>

```json
{
    "power": true,
    "bri": 150,
    "hue": 0,
    "sat": 255,
    "effect": "fade",
    "time": 1000
}
```

### 1.3. Read from device

/api/get/<addr>

```json
{
    "power": false
}
```

## 2. Device types

### 2.1. Button

### 2.2. Light
