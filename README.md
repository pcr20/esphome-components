# esphome-components

External components for [ESPHome](https://esphome.io). Each one only uses ESPHome's public
component interfaces and does not replace any built-in component, so it keeps building across
ESPHome releases.

| Component | |
|---|---|
| [`modbus_sniffer`](docs/goa-heatpump/modbus-sniffer.md) | Passive Modbus RTU bus monitor. It never transmits: it decodes every frame on the bus, keeps a register image per block and accounts for every byte (CRC errors, unknown frames, lost bytes). |

## Use

Pin a release tag, not a branch, so an ESPHome rebuild never picks up different code:

```yaml
external_components:
  - source: github://pcr20/esphome-components@v0.1.0
    components: [modbus_sniffer]
```

## Goa heat pump notes

`docs/goa-heatpump/` holds the RS-485 bus map of the Goa heat pump the sniffer was written for,
an example configuration, and the Python tools used to check the parser against captures
(`tools/sniffer_check.py --selftest`).

## History

Moved from `pcr20/esphome` (branch `modbus_sniffer_v2`, up to commit `9fd1718d0`) with its
history; the component was at `esphome/components/modbus_sniffer` there.

## License

The same terms as ESPHome (MIT for the Python code, GPLv3 for the C++ code); see [LICENSE](LICENSE).
