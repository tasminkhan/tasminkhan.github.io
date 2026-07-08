---
layout: page
title: Voltage-Controlled LC Cross-Coupled Oscillator (855–881 MHz)
description: LC cross-coupled VCO designed and laid out in Cadence Virtuoso with proper W/L sizing, achieving a low phase noise of –157.9 dBc/Hz.
img: assets/img/projects/vco/layout.jpg
importance: 3
category: hardware
# github: # TODO: add repository URL
---

Designed and laid out a voltage-controlled LC cross-coupled oscillator for the 855–881 MHz range in Cadence Virtuoso, with proper transistor sizing (W/L) and a low phase noise of –157.9 dBc/Hz.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/vco/schematic.png" title="VCO schematic" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/vco/layout.jpg" title="VCO layout" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Cross-coupled VCO schematic (left) and layout (right).
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/vco/freq-vs-vctrl.jpg" title="Control voltage vs. frequency" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/vco/power-vs-vctrl.jpg" title="Control voltage vs. output power" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/vco/phase-noise.jpg" title="Phase noise at 0.5 V control voltage, 1 MHz offset" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Control voltage vs. frequency, control voltage vs. output power, and phase noise (0.5 V control voltage, 1 MHz offset).
</div>
