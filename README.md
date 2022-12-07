# AsiNine-Pyramid
Schematic and layout in Eagle PCB for a quad bm1387 standalone miner
// skip if deemed off topic
// Other versions made
// A single BM1391 version, obsolete as information on the asic is too scarce
// Asinine Pharaonis: dual BM1387 version, compatible with the quad version (this)
// Motivation:
// I'm running an ESP32C3 with a RGB LED to monitor traffic (flickers on inbound TX's and glows on memory pool size) to my node.
// Why not let it do something useful?

Properties (concept):
- Standalone miner to be connected to a mining pool or a private Bitcoin node that will serve the work (over websocket)
- Size: 80x60mm
- Programmable Vcore for the bm1387 asics
- ws2812 led for special effects ;)
- max. power usage targeted at ~10-15W
- Cooling: M.2 SSD cooler or recycled S9 heatsinks, tiewrapped to the board

Major parts used:
- 4x BM1387xx asics (tested bm1387bf & bm1387b)
- ESP32-C3-mini-1
- SY8208A or B step down regulator (8A) (currently controlled by PWM, considering a cheap ($0.10) DAC)
- XC6206P-18 lin. regulators for 1.8 & 0.8V
- SY8009B step down regulator (overkill) for the esp32c3
- usb-c connector for power (5V)

Revision
v0.2 7-12-2022
* Alpha version, all bugs from v0.1 corrected
v0.1 29-10-2022
* pre alpha version
* Function tested ok after some debugging
