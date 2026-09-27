---
title: AXI4-interconnect with weighted arbiter for fair SoC bandwidth distribution
category: research
importance: 4
submitted: true # shows a "Manuscript Submitted" tag
# Grey spec chips shown under the title: [label, value]
badges:
  - ["flow", "RTL to GDSII"]
  - ["PDK", "ASAP7"]
  - ["HDL", "SystemVerilog"]
  - ["Cadence", "Genus · Innovus"]
  - ["scripting", "TCL"]
  - ["traffic sim", "SystemVerilog TB"]

highlights:
  - "Designed a 3×3 AXI4 crossbar in SystemVerilog with three arbitration policies: round robin, priority based, and priority-aware deficit round robin"
  - "priority-aware DRR charges each grant in beats, keeping every burst whole while bringing two equal-weight masters from 1:16 to 1:1 bandwidth parity at full load"
  - "Cut latency-critical read latency from 95 to 37 cycles — 190 ns to 74 ns at 500 MHz — a 61% reduction over round robin"
  - "Took all three policies RTL-to-GDSII on ASAP7 7-nm under one shared traffic generator and measured the per-policy area, power, and timing cost"

slides:
  - assets/img/research/axi/thumbnail.jpg
  - assets/img/research/axi/traffic.jpg
  - assets/img/research/axi/chip.png
  - assets/img/research/axi/power.jpg
  - assets/img/research/axi/row.jpg
github: https://github.com/tasminkhan/AXI_interconnect
---
