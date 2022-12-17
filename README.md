# aSiNine Pyramid<br>
Schematic and layout in Eagle PCB for a quad bm1387 standalone miner<br>
// skip if deemed off topic!<br>
// Other versions made<br>
// A single BM1391 version, obsolete as information on the asic is too scarce<br>
// aSiNine Pharaonis: dual BM1387 version, compatible with the quad version (this)<br>
// Unnamed project single BM1397 (in pre-alpha stage, pcb's are on the slow boat from China)<br>
<br>
Motivation:
I'm running an ESP32C3 with a RGB LED to monitor traffic (flickers on inbound TX's and glows on memory pool size) to my node.<br>
Why not let it do something useful while idle?<br>
<br>
Properties (concept):
- Standalone miner to be connected to a mining pool or a private Bitcoin node that will serve the work (over websocket)
- Size: 80x60mm
- Programmable Vcore for the bm1387 asics
- ws2812 led for special effects ;)
- max. power usage targeted at ~10-15W
- Cooling: M.2 SSD cooler or recycled S9 heatsinks, tie-wrapped to the board, fan not considered yet.
- Low(est) cost possible!

Major parts used:
- 4x BM1387xx asics (tested bm1387bf & bm1387b)
- ESP32-C3-mini-1
- SY8208A or B step down regulator (8A) <s>(currently controlled by PWM, considering a cheap ($0.10) DAC)</s> controlled by a dac.
- XC6206P-18 lin. regulators for 1.8 & 0.8V
- SY8009B step down regulator (overkill) for the esp32c3, limiting the power supply to 5V only..
- usb-c connector for power (5V) and debugging

Revisions<br>
<br>* Don't build anything alpha, components and schematic/layout will change in future revisions. *<br>
v0.2-alpha 7-12-2022 upto today<br> Not actually built/tested yet.<br>
All bugs from v0.1 corrected and changes incorporated in the design.<br>
<br>
v0.1 29-10-2022<br> Debugging stage<br>
pre alpha version<br>
(For the unpublished 2 asic version (Pharaonis): Added a pt8211 DAC to control Vcore instead of a PWM from the esp32c3, the pwm caused some problems during wifi transfers and reconnects. I'm currently working on this version, some results found during testing: power usage ~2.8W @ <s>44GH/s</s> ~40GH/s, so it can be passively cooled.)<br>
!BM1387 apparently only seaches through roughly 4000 mega nonces out of the 4.295 mega nonces available...!<br>
Function tested ok <s>but unstable (related to pwm)</s><br>
todo: <s>final speccing of decoupling capacitors, redo some of the power&ground planes, more stability testing, add dac to schematic and layout</s>, change mounting holes for heatsink.<br>
