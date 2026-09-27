---
title: A CNN Neuron for Always-On Near-Sensor Inference in 7nm Technology
category: research
importance: 3
submitted: true # shows a "Manuscript Submitted" tag
github: https://github.com/tasminkhan/CNFET7-nm_CNN_Neuron
# Grey spec chips shown under the title: [label, value]
badges:
  - ["flow", "RTL to GDSII"]
  - ["PDK", "CNFET7 · ASAP7"]
  - ["Cadence", "Genus · Innovus"]
  - ["scripting", "TCL"]
  - ["HDL", "SystemVerilog"]

highlights:
  - "Designed and implemented a quantized CNN neuron for fixed point arithmetic through a full RTL-to-GDSII flow in the open-source CNFET7 carbon-nanotube library"
  - "Post-route neuron is 1.24× faster with 59.2% lower dynamic power than an identical ASAP7 FinFET build; a 3.6× energy-delay-product advantage"
  - "Per-instance normalization shows that the area penalty is a library-maturity effect: CNFET7 cells are 17.1% smaller per instance but 66.7% more numerous"

slides:
  - assets/img/research/cnfet/neuron.png
  - assets/img/research/cnfet/cnfet.png
  - assets/img/research/cnfet/asap7.png
  - assets/img/research/cnfet/Power.png
  - assets/img/research/cnfet/spider.png
---
