# Panlee ESP32-S3 4848 (GC9503V)

ESPControl profile for the 480 × 480 Panlee panel using the ESP32-S3, 16 MB flash,
octal 80 MHz PSRAM, GC9503V MIPI RGB display, FT63x6 touchscreen and GPIO5
backlight.

The display driver is sourced from the `gc9503v` branch of
[`GiorgioAresu/esphome`](https://github.com/GiorgioAresu/esphome/tree/gc9503v),
which is required until GC9503V support is available in the ESPHome version
used by this project. The device profile intentionally has no built-in relay
configuration.

For local development, provide `wifi_ssid` and `wifi_password` in your ESPHome
`secrets.yaml`, then run `esphome run dev.yaml`. For a dashboard import, use
`esphome.yaml`.
