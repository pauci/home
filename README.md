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

### 1.2. Read from device

```
/api/get/<addr>
```

```json
{
    "power": false
}
```

### 1.3. Write to device

```
/api/set/<addr>
```

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

## 2. Device types

### 2.1. Button

#### 2.1.1. Attributes

<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th></th>
  </tr>
  <tr>
    <td>pressed</td>
    <td>boolean</td>
    <td>Determines whether button is pressed</td>
    <td>Read only</td>
  </tr>
</table>

### 2.2. Light

#### 2.1.1. Attributes

<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th></th>
  </tr>
  <tr>
    <td>power</td>
    <td>boolean</td>
    <td>Determines whether light is powered on</td>
    <td>R/W</td>
  </tr>
  <tr>
    <td>br</td>
    <td>uint8</td>
    <td>Brightness</td>
    <td>R/W</td>
  </tr>
  <tr>
    <td>hue</td>
    <td>uint8</td>
    <td>Hue</td>
    <td>R/W</td>
  </tr>
  <tr>
    <td>sat</td>
    <td>uint8</td>
    <td>Saturation</td>
    <td>R/W</td>
  </tr>
  <tr>
    <td>effect</td>
    <td>string</td>
    <td>
    <ul>
        <li>"fade"   - linear fade to the new state</li>
        <li>"fall"   - accelerating fade to the new state</li>
        <li>"dive"   - decelerating fade to the new state</li>
        <li>"loop"   - linear fade to the new state and back</li>
        <li>"bounce" - fall to the new color and back</li>
        <li>"swing"  - dive to the new color and back</li>
      </ul>
    </td>
    <td>R/W</td>
  </tr>
  <tr>
    <td>time</td>
    <td>uint16</td>
    <td>Effect transition time in ms</td>
    <td>R/W</td>
  </tr>
  <tr>
    <td>repeat</td>
    <td>boolean</td>
    <td>Effect repeat</td>
    <td>R/W</td>
  </tr>
</table>

