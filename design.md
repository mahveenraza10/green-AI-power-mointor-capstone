
## Wiring Plan

| Component | Pico 2W Pin | Notes |
|---|---|---|
| INA219 SDA | GP4 (pin 6) | I2C0 |
| INA219 SCL | GP5 (pin 7) | I2C0 |
| INA219 VCC | 3V3 | |
| INA219 GND | GND | |
| LED Bar Graph | GP10–GP17 | 8 segments, through 220Ω each |
| Status LED | GP18 | Through 330Ω |
| Buzzer | GP19 | Active buzzer, threshold alert |
| Push Button | GP20 | Pull-down, cycles display mode |
| Potentiometer | GP26 (ADC0) | Sets power alert threshold |

*Pin assignments are provisional — will finalize during breadboard testing.*

## Measurement Approach

1. **What we measure:** Voltage (V) and current (mA) across the INA219 shunt resistor on the 5V USB line
2. **Derived values:** Power (mW) = V × I, Energy (mWh) = accumulated power over time
3. **CO2e estimate:** Energy (kWh) × grid carbon intensity (Ontario avg ~30 g CO2e/kWh)
4. **Sample rate:** ~10 readings/sec from INA219, averaged per second for dashboard
5. **Test loads:**
   - Raspberry Pi idle vs under CPU stress
   - USB LED lamp (baseline/known draw)
   - Pico running different AI-adjacent workloads
6. **Controls:** Each test run 3×, 60 seconds minimum, room temp logged

## Open Questions

- [ ] Is 10 Hz sample rate enough to catch power spikes?
- [ ] Which CO2e grid factor to use — Ontario average or real-time?
- [ ] Should the potentiometer threshold persist across power cycles (EEPROM)?
