---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

---

## Ultra-Low-Power Computing Platforms and Architectures 

- **Programming Models and Compilation Support for Energy-Minimal CGRAs**

  A new class of low-power sensor devices are emerging at the <em>extreme edge</em> in conjunction
  with new app/device domains such as wildlife monitoring, nanosatellites, medical wearables, and
  more. These devices need to operate at <em>ultra-low-power</em> (ULP, μWs) while supporting a variety of 
  complex applications (on-device inference, DSP, etc.) to be feasible at all. Otherwise, 
  a large number of these devices will be impossible to maintain if they all run out of power
  in a matter of weeks or months. 

  Consequently, the underlying compute must achieve high <em>flexibility</em> and 
  <em>energy-efficiency</em>. We think <em>coarse-grained reconfigurable arrays</em> (CGRAs),
  a class of spatial dataflow architectures, are a great choice for these devices as they 
  strike a balance between both dimensions.

  CGRAs are roughly defined as a grid processing elements (PEs) connected via a network-on-chip
  (NoC). They achieve efficiency by spatially distributing "coarse" operations (like ALU or memory
  ops) onto PEs and communication onto the NoC -- both of which eliminate expensive fetch/decode in a 
  shared pipeline and costly updates to shared register files. However, prior ULP CGRAs only 
  accelerate portions of an app (namely affine inner loops), leaving the rest of the code to 
  run on inefficient in-order scalar cores and increasing switching costs. This creates a clear
  Amdahl efficiency bottleneck for these architectures.

  Our insight is that supporting <em>entire apps</em> on an energy-minimal CGRA is key to improving
  efficiency and addressing this bottleneck. This requires support for arbitrary computation 
  (including complex control-flow, irregular memory acceses, and operation ordering).

  We're working on **RipTide** to realize this insight; it is a co-designed compiler and ULP CGRA 
  architecture that achieves both high programmability and extreme energy efficiency. RipTide provides 
  a rich set of program primitives that support arbitrary control flow and irregular memory accesses. 
  It also enforces memory ordering through careful analysis at compile-time, eliminating the need for 
  expensive tag-token matching on fabric. RipTide also observes that control-flow operations are simple, 
  but prevalent, so allocating them valuable PE resources is wasteful. Instead, RipTide offloads these 
  operations into its on-chip network, reusing existing switch hardware. RipTide compiles applications 
  entirely written in C while saving 25% energy v. the state-of-the-art ULP CGRA.

  You can see [RipTide](https://souradipghosh.com/pubs-talks/) at MICRO '22, later in October.

  This work builds on [SNAFU](https://g-ram.github.io/files/snafu_isca_2021.pdf), 
  an energy-minimal CGRA generation framework and architecture. 

  **In collaboration with:** [Abstract Research Group](http://abstract.ece.cmu.edu/) 
  and [CORGi](https://cmu-corgi.github.io/)

---

[Archive (from NU)](https://souradipghosh.com/archive-research-nu/).
