Originally a Tokyo Night forked from [https://github.com/fabioluciano/tmux-tokyo-night](abioluciano/tmux-tokyo-night) ---

## Features

- [Transparency support](#Transparency-examples)

## Plugins

- **Datetime** - Show datetime;
- **Weather** - Show weather;
- **Playerctl** - Show playerctl;
- **Spt** - Show Spotify;
- **Homebrew** - Show Homebrew;
- **yay** - Show yay;
- **battery** - Show battery;

## Install

Add plugin to the list of `TPM` plugins in `.tmux.conf`:

```
set -g @plugin 'ChadLefort/tmux-theme'
```

Hit <kbd>prefix</kbd> + <kbd>I</kbd> to fetch the plugin and source it. You can now use the plugin.

## Available Configurations

| Configuration                       | Description      | Avaliable Options                                                       | Default            |
| ----------------------------------- | ---------------- | ----------------------------------------------------------------------- | ------------------ |
| `@theme_variation`                  |                  | `dark`                                                                  | `dark`             |
| `@theme_active_pane_border_style`   |                  |                                                                         | `#737aa2`          |
| `@theme_inactive_pane_border_style` |                  |                                                                         | `#292e42`          |
| `@theme_left_separator`             |                  |                                                                         | ``                |
| `@theme_right_separator`            |                  |                                                                         | ``                |
| `@theme_window_with_activity_style` |                  |                                                                         | `italics`          |
| `@theme_status_bell_style`          |                  |                                                                         | `bold`             |
| `@theme_plugins`                    |                  | `datetime`, `weather`, `playerctl`, `spt`, `homebrew`, `yay`, `battery` | `datetime,weather` |
| `@theme_disable_plugins`            | Disables plugins | `1`, `0`                                                                | `0`                |

## Plugins

### Datetime

> Prints informations about the current date and time.

| Configuration                              | Description | Avaliable Options | Default                   |
| ------------------------------------------ | ----------- | ----------------- | ------------------------- |
| `@theme_plugin_datetime_icon`              |             | Any character 📅  | Nerd Font 'Calendar' icon |
| `@theme_plugin_datetime_accent_color`      |             |                   |                           |
| `@theme_plugin_datetime_accent_color_icon` |             |                   |                           |
| `@theme_plugin_datetime_format`            |             |                   |                           |

### Weather

> Prints informations about the current weather. It uses `jq` to parse the response. Make shure to have it;

| Configuration                             | Description                               | Avaliable Options                                               | Default                     |
| ----------------------------------------- | ----------------------------------------- | --------------------------------------------------------------- | --------------------------- |
| `@theme_plugin_weather_icon`              |                                           | Any character 🌡️                                                | Font Awesome 'Cloud' icon   |
| `@theme_plugin_weather_accent_color`      |                                           |                                                                 |                             |
| `@theme_plugin_weather_accent_color_icon` |                                           |                                                                 |                             |
| `@theme_plugin_weather_format`            | Format for displaying weather information | `%t`, `%c`, `%h`, `%w` (temperature, condition, humidity, wind) | `%t+H:%h`                   |
| `@theme_plugin_weather_location`          | Location for weather (city/country)       | `"City, Country"`                                               | IP-based location detection |

#### Example

```
set -g @theme_plugin_weather_location 'Blacksburg, United States'
```

### Playerctl

> Prints informations about the current song playing. Does not work in `MacOS`, because it uses `MPRIS`, and is only available in `Linux`.

| Configuration                               | Description | Avaliable Options | Default |
| ------------------------------------------- | ----------- | ----------------- | ------- |
| `@theme_plugin_playerctl_icon`              |             |                   |         |
| `@theme_plugin_playerctl_accent_color`      |             |                   |         |
| `@theme_plugin_playerctl_accent_color_icon` |             |                   |         |
| `@theme_plugin_playerctl_format`            |             |                   |         |

### Battery

Shows battery charging status (charging or discharging) and battery percentage.

| Configuration                                    | Description                        | Avaliable Options | Default  |
| ------------------------------------------------ | ---------------------------------- | ----------------- | -------- |
| `@theme_plugin_battery_charging_icon`            | Icon to display when charging      | Any character     |         |
| `@theme_plugin_battery_discharging`              | Icon to display when on battery    | Any character     | 󰁹        |
| `@theme_plugin_battery_red_threshold`            | Show in red when below this %      | 0-100             | 10       |
| `@theme_plugin_battery_yellow_threshold`         | Show in yellow when below this %   | 0-100             | 30       |
| `@theme_plugin_battery_red_accent_color`         | Color when < red threshold         | Palette color     | red      |
| `@theme_plugin_battery_red_accent_color_icon`    | Icon color when < red threshold    | Palette color     | magenta2 |
| `@theme_plugin_battery_yellow_accent_color`      | Color when < yellow threshold      | Palette color     | yellow   |
| `@theme_plugin_battery_yellow_accent_color_icon` | Icon color when < yellow threshold | Palette color     | orange   |
| `@theme_plugin_battery_green_accent_color`       | Color when > yellow threshold      | Palette color     | blue7    |
| `@theme_plugin_battery_green_accent_color_icon`  | Icon color when > yellow threshold | Palette color     | blue0    |
