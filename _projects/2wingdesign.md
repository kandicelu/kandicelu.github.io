---
layout: project
title: ANSYS Wing Optimization
images:
  - /assets/images/wingskel.png
---
**Technical Skills:** Structural Analysis · CAD · FEA · ANSYS Optimization

For my Finite Element Analysis class, we were tasked with analyzing and optimizing an airplane wing using ANSYS. The overall geometry, material, and loading of the wing was fixed, with our design variables being the number and location of spars and ribs, as well as the thickness of the skin, spars, and ribs. Our goal was to minimize weight while remaining within a maximum deflection of 0.375, and safety factor of 1.5 (corresponding with a max stress of 252 MPa)

The geometry was modelled in ANSYS Mechanical using shell elements, with one end fixed and optimized both manually, and using surface response optimization. Our preliminary design consisted of 2 spars and 2 ribs, and weighed 10390 kg. After analyzing various configurations, a design with 4 equally spaced spars, and one rib was found to be optimal. This final design weighed 7808.8 kg marking a mass reduction of nearly 25%, with a maximum deflection of 0.3747m, and maximum stress of 165 MPa, corresponding to a safety factor of 2.3. 

![Deflection Results]({{ "/assets/images/wingdefl.png" | relative_url }}){:style="width: 600px"}
![Stress Results]({{ "/assets/images/wingstressfull.png" | relative_url }}){:style="width: 600px"}

Mesh refinement tests were conducted to ensure convergence of these values. An adaptive convergence test showed our deflection converging to within 0.01% change. Small stress singularities occured where overlapping shells were fixed, preventing convergence upon refinement. To avoid this, small cutouts were created around the singularities and manual mesh refinement was performed around the high stress regions, leading to convergence within 1% change.

![Stress Convergence]({{ "/assets/images/wingstressconv.png" | relative_url }}){:style="width: 400px"}
![Stress Cutout]({{ "/assets/images/wingstress.png" | relative_url }}){:style="width: 550px"}