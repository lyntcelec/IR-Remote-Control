# ir-remote-control

Remote Control for IR TV WebOS

## Color Management

color customization implemented through the section

```yaml
colors:
```

- buttons: set buttons background color - default: "#f2f0fa"
- texts: set buttons color - default: "var(--primary-text-color)"
- background: set remote background color - default: "var(--primary-background-color)"

```yaml
colors:
  buttons: var(--deactive-background-button-color)
  texts: pink
  background: rgba(95,155,234)
```

**NOTE: option in "your-theme.yaml**

```yaml
#button
deactive-background-button-color: "#f2f0fa"
```

## hacs Card install

1. Find and install `IR Remote Control` plugin

2. Add a reference inside your resources config:

```yaml
resources:
  - type: module
    url: /hacsfiles/ir-remote-control/ir-remote-control.js
```

### Manual install

1. Download and copy `ir-remote-control.js` from (https://github.com/lyntcelec/ir-remote-control) into your custom components directory.

2. Add a reference `ir-remote-control.js` inside your resources config:

```yaml
resources:
  - url: /local/"your_directory"/ir-remote-control.js
    type: module
```

# lovelace config: default view

```yaml
type: custom:ir-remote-control
entity: remote.rm3
device: tivi
color_buttons: enable
remap:
  - UP: up
    DOWN: down
```

### Main Options

| Name            | Type        | Default      | Supported options          | Description                                                                                                                                                                                                                                                   |
| --------------- | ----------- | ------------ | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`          | string      | **Required** | `custom:ir-remote-control` | Type of the card                                                                                                                                                                                                                                              |
| `entity`        | string      | **Required** |                            | tv entity                                                                                                                                                                                                                                                     |
| `device`        | string      | **Option**   |                            | Device ID to send command to.                                                                                                                                                                                                                                 |
| `name`          | string      | **Option**   |                            | tv name                                                                                                                                                                                                                                                       |
| `colors`        | string      | **Option**   |                            | list of color options                                                                                                                                                                                                                                         |
| `color_buttons` |             | **Option**   | enable                     | display color buttons: RED GREEN YELLOW BLUE                                                                                                                                                                                                                  |
| `remap`         | object list | **Option**   |                            | list of key to remap: 1, 2, 3, 4, 5, 6, 7, 8, 9, 0, MENU, INPUT, UP, LEFT, RIGHT, DOWN, HOME, BACK, ENTER, EXIT, MUTE, INFO, CHANNELUP, CHANNELDOWN, RED, GREEN, YELLOW, BLUE, POWER, VOLUME_UP, VOLUME_DOWN, PLAY, PAUSE, STOP, REWIND, RECORD, FAST_FORWARD |

### Colors Options

| Name          | Type   | Default                 | Supported options | Description              |
| ------------- | ------ | ----------------------- | ----------------- | ------------------------ |
| `buttons`     | string | **Option**              | color formats     | buttons background-color |
| `texts`       | string | **Option**              | color formats     | number and icon color    |
| `background:` | string | **Option**              | color formats     | list of color options    |
| `border:`     | string | --app-header-text-color | color formats     | remote border color      |

### dimensions Options

| Name           | Type | Default    | Supported options | Description                          |
| -------------- | ---- | ---------- | ----------------- | ------------------------------------ |
| `scale`        |      | **Option** | number            | scale factor; default 1              |
| `border_width` |      | **Option** | number            | set remote border width; default 1px |

## Popup Buttons

![all](example/popup.png)
