---
layout: page
title: Three-Band Digital Audio Equalizer Peripheral
description: 16-bit fixed-point biquad IIR filters (Icarus Verilog), verified with cocotb Python testbenches and implemented as a RISC-V peripheral for digital audio processing.
img: assets/img/projects/equalizer/frequency-analysis.png
importance: 1
category: hardware
# github: # TODO: add repository URL
---

Designed a three-band audio equalizer with 16-bit fixed-point biquad IIR filters, compiled using Icarus Verilog and verified with cocotb Python testbenches, implementing a RISC-V peripheral for digital audio processing.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/equalizer/frequency-analysis.png" title="Frequency-response analysis" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Frequency-response analysis of the three-band equalizer.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/equalizer/filtered-waves.png" title="Filtered waveforms" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/equalizer/schematic.png" title="Elaborated schematic" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Filtered output waveforms (left) and the elaborated RTL schematic (right).
</div>
