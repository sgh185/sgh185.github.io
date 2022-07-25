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

  A coarse-grained reconfigurable arrays (CGRA) is a dataflow architecture
  with configurable processing elements (PEs) that offers programmability 
  <em>and</em> high energy efficiency. A program written for a CGRA typically
  requires optimizing compiler support to map the program's dataflow graph
  onto the processing elements in order to effectively use the CGRA's resources.

  I'm exploring language support, compilation approaches, and dataflow graph 
  optimizations for CGRAs and related architectures. We're working on
  RipTide, a new CGRA compiler and architecture that achieves efficiency by offloading
  entire applications to the fabric and handling common programming idioms. This 
  includes CGRA support for complex control-flow, irregular memory accesses, enforced 
  memory ordering, and more. 
  
  This work builds on [SNAFU](https://g-ram.github.io/files/snafu_isca_2021.pdf), 
  an energy-minimal CGRA generation framework and architecture. 

  **In collaboration with:** [Abstract Research Group](http://abstract.ece.cmu.edu/) 
  and [CORGi](https://cmu-corgi.github.io/)

---

[Archive (from NU)](https://souradipghosh.com/archive-research-nu/).
