# ZMK nice!view Custom Shield

A custom [nice!view](https://nicekeyboards.com/nice-view) shield for [ZMK firmware](https://zmk.dev/).

## Overview

This is a custom display widget shield that provides a custom status screen for the nice!view low-power, high-refresh-rate display. It replaces the default ZMK nice!view widgets with a tailored design.

## Features

- Custom vertical status widget for the nice!view display
- BLE profile indicators showing the status of the first five profiles (1-5)
- Visual indicators for connection state:
  - **Solid outline**: connected
  - **Dashed outline**: not connected
  - **No outline**: not bound
- Support for split keyboard configurations (central and peripheral)

## Requirements

- A `&nice_view_spi` labeled SPI bus with at least MOSI, SCK, and CS pins defined

## Configuration

Add the following to your keymap or config file to enable the shield:

```
CONFIG_ZMK_DISPLAY=y
CONFIG_NICE_VIEW_CUSTOM=y
```

## Disable Custom Widget

To revert to the built-in ZMK widget instead of the custom one, add the following to your `.conf` file:

```
CONFIG_ZMK_DISPLAY_STATUS_SCREEN_BUILT_IN=y
CONFIG_ZMK_LV_FONT_DEFAULT_SMALL_MONTSERRAT_26=y
CONFIG_LV_FONT_DEFAULT_MONTSERRAT_26=y
```

## Project Structure

```
boards/shields/nice_view_custom/
├── CMakeLists.txt
├── Kconfig.defconfig
├── Kconfig.shield
├── nice_view_custom.conf
├── nice_view_custom.overlay
├── nice_view_custom.zmk.yml
├── custom_status_screen.c
└── widgets/
    ├── art.c
    ├── bolt.c
    ├── bt18.c
    ├── left_art.c
    ├── peripheral_status.c
    ├── peripheral_status.h
    ├── profiles.c
    ├── status.c
    ├── status.h
    └── util.c
    └── util.h
```

## License

MIT (see ZMK upstream for full license details)
