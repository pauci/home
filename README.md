Home
====

## 1. Home API

### 1.1. Device discovery

#### 1.1.1. Description

#### 1.1.2. Request
```
/api/discover
```

#### 1.1.3. Request example

```json
{
    "new": false,
    "types": [
        "button",
        "switch",
        "rotary",
        "motion",
        "temperature",
        "humidity",
        "light",
        "display"
    ]
}
```

#### 1.1.4. Response

Address indexed list of discovered devices.

#### 1.1.5. Response example

```json
{
	"101": {
		"type": "switch"
	},
	"120": {
		"type": "motion"
	},
	"201": {
		"type": "light",
		"dimmable": true,
		"chromatic": false
	},
	"202": {
		"type": "light",
		"dimmable": true,
		"chromatic": true
	}
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

#### 2.1.1. Description

```json
{
    "type": "button"
}
```

#### 2.1.2. Attributes

<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th></th>
  </tr>
  <tr>
    <td>value</td>
    <td>boolean</td>
    <td>Determines whether button is pressed</td>
    <td>Read only</td>
  </tr>
</table>

### 2.3. Switch

#### 2.3.1. Description

```json
{
    "type": "switch"
}
```

#### 2.3.2. Attributes

<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th></th>
  </tr>
  <tr>
    <td>value</td>
    <td>boolean</td>
    <td>Determines whether switch is in on or off position</td>
    <td>Read only</td>
  </tr>
</table>

### 2.2. Motion sensor

#### 2.2.1. Description

```json
{
    "type": "motion"
}
```

#### 2.2.2. Attributes

<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th></th>
  </tr>
  <tr>
    <td>alarm</td>
    <td>boolean</td>
    <td>Motion detected</td>
    <td>Read only</td>
  </tr>
</table>

### 2.4. Relay

#### 2.4.1. Description

```json
{
    "type": "relay"
}
```

#### 2.4.1. Attributes

<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th></th>
  </tr>
  <tr>
    <td>state</td>
    <td>boolean</td>
    <td>Relay state</td>
    <td>R/W</td>
  </tr>
</table>

### 2.5. Light

#### 2.5.1. Description

```json
{
    "type": "light",
    "dimmable": true,
    "chromatic": true,
    "count": 1
}
```

Count is a number of independetly controllable light segments. (e.g. the number of leds in addressable led strip)

#### 2.5.2. Attributes

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
        <li>"fade"   - linear fade to the new color</li>
        <li>"fall"   - accelerating fade to the new color</li>
        <li>"dive"   - decelerating fade to the new color</li>
        <li>"loop"   - linear fade to the new color and back</li>
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

