---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

---

## The Interweaving Project
The numerous pieces of a computer systems stack (the compiler, the OS, the 
architecture, etc.) are usually considered as separate entities. What if 
these entities weren't strictly separated -- what if these pieces were
"interwoven" or "blended"? The Interweaving Project explores the feasibility, 
efficiency, and the performance of these systems, with a focus on parallel
systems. More info [here](http://interweaving.org/).

The following are projects in this research direction that I've contributed to:

- **Compiler-Timing**

  We developed the compiler-timing model as a high-performing, low-overhead 
  mechanism to replace timer interrupts and traditional interrupt handling 
  in a kernel, which is often used to drive a generic threads implementation. 
  We found that using compiler-timing to drive a fast fibers (cooperatively 
  scheduled threads) implementation in a kernel can effectively achieve 
  preemptive scheduling at a very fine-grain -- enabling the possibility
  to extract parallelism at a fine granularity. The system can perform up to
  16x faster than Linux threads. 

  The original framework achieves a soft timing guarantee by performing static 
  analyses on a piece of code and injecting callbacks that are set to execute 
  a specified interval or granularity. In other words, the compiler can be timing-aware
  using custom analyses. The original framework was written using LLVM and the Nautilus Aerokernel. 
  (See [paper](https://souradipghosh.com/pubs-talks/)).
 
  We are currently developing a version of compiler-timing for user-space
  to drive a variety of systems using compiler-injected callbacks
  ([heartbeat scheduling](http://www.andrew.cmu.edu/user/mrainey//heartbeat/heartbeat.html),
  new techniques to analyze performance of address translation). 
 
  **In collaboration with:** Prescience Lab, NU Compilers Group, Illinois Institute 
  of Technology's [HExSA Lab](http://cs.iit.edu/~khale/lab/index.html), Carnegie Mellon, 
  NU Parallel Architecture Group

- **Compiler and Runtime-Based Address Translation** (CARAT)

  We are building on [CARAT](http://pdinda.org/Papers/pldi20.pdf), a novel framework to replace virtual 
  memory and paging with a fully-software implementation consisting of compiler transforms
  and a runtime. Our goal is to explore an implementation of CARAT, 
  originally written in user-space, in a kernel (Nautilus). This is
  a non-trivial task, as we have to understand methods to track and 
  protect memory in the kernel, efficiently search and query memory 
  regions, apply user-space compiler transforms to the entire kernel, 
  and reduce the overhead of patching and protecting memory.
  
  See some of our [progress](https://souradipghosh.com/pubs-talks/).
 
  **In collaboration with:** Prescience Lab, NU Compilers Group, NU Parallel Architecture Group

- **Floating-Point Virtual Machine** (FPVM)

  We are expanding on work done to record the floating-point behavior
  of scientific applications ([FPSpy](http://pdinda.org/Papers/hpdc20.pdf)). We want to track and correct 
  floating-point arithmetic that generate exceptions by automatically 
  integrating codebases with an alternative FP arithmetic system. We are 
  investigating several techniques, including the use of compiler instrumentation
  to check correctness and exception state on floating-point
  operations and a custom runtime to correct erroring operations using
  the [MPFR](https://www.mpfr.org/) library.
 
  **In collaboration with:** Prescience Lab 


## Next Generation Compilers 
Investigating and developing novel compiler optimization and code generation 
techniques for the next generation of compilers. 

The following are projects in this research direction that I've contributed to:
 
- **Noelle**

  We have built Noelle as a middle-end compiler layer designed on top 
  of LLVM to provide new abstractions and parallelizing capabilities 
  that give developers the tools to build advanced code analyses and 
  transformations with just a few lines of code. 

  My research contributions include investigating and developing 
  compiler "enablers" to assist Noelle's parallelization capabilities 
  and designing and building an instruction scheduler engine for 
  users to utilize -- whether it be to parallelize code or for 
  applying custom analyses and transformations. Custom scheduling  
  techniques achieved speedups across a wide array of benchmarks
  in Noelle's benchmark suite.
 
  See our [paper](https://souradipghosh.com/pubs-talks/) and some of our 
  [progress](https://users.cs.northwestern.edu/~simonec/Software.html).

  **In collaboration with:** NU Compilers Group, Princeton's [Liberty
  Research Group](https://liberty.princeton.edu/) 

- **New Foundations for Instruction Scheduling**

  Instruction scheduling has consistently been a cornerstone of the 
  compiler back-end, where it is used for optimization and to extract
  ILP. However, little work has been done to apply automatic, general 
  purpose global code scheduling mechanisms to the IR, where dependence 
  analysis and code transformations are much more powerful. 

  We are exploring a new compiler relation to 1) understand how often 
  instructions or basic blocks in the IR execute relatively, and 2) to relax 
  dependences for code motion so that middle-end instruction scheduling is 
  effective. 

  We're simultaneously expanding the scheduler abstraction in Noelle with these 
  concepts, and we've applied it to an automatic parallelization framework within 
  Noelle ([HELIX](https://users.cs.northwestern.edu/~simonec/files/Research/papers/HELIX_CGO_2012.pdf)). 
  The abstraction is designed as a hierarchy of schedulers -- with 
  schedulers handling more and more complex control-flow structures (basic 
  blocks, loops, sub-CFGs, etc.). 
 
  See some of our [progress](https://souradipghosh.com/pubs-talks/).

  **In collaboration with:** NU Compilers Group 

- **TimeSqueezer**

  We are expanding upon the [TimeSqueezer](https://users.cs.northwestern.edu/~simonec/files/Research/papers/RES_ISCA_2019.pdf)
  stack to further explore energy savings and efficiency with a novel 
  hardware-software co-design aimed at automatically reducing the 
  amount of memory used by arithmetic instruction operands. This system
  targets embedded systems and tiny devices. 

  My research contributions include designing and building middle-end 
  code analyses and transformations for this new approach.  

  **In collaboration with:** NU Compilers Group, NU TimeSqueezing Group 

- **Compiler-Optimized Checkpointing for Intermittent Systems**

  Energy-harvesting devices operate intermittently -- i.e. only when
  energy is available to power the system. A common design in intermittent
  systems is the use of checkpointing (see [more](https://sampa.cs.washington.edu/new/papers/mspc14-time-machine.pdf)). 
  Checkpoints could be introduced by the programmer or automatically by the 
  compiler. We are exploring compiler optimziations to reduce the number of 
  checkpoints introduced automatically, without user input, and for general 
  purpose applications. 

  My contributions include middle-end compiler transformations that exploit 
  dependence analyses and instruction scheduling algorithms to reduce inserted 
  checkpoints in loops. 

  **In collaboration with:** NU Compilers Group, TU Delft's [Sustainable Systems 
  Laboratory](https://github.com/tudssl/), NU's [Ka Moamoa Lab](http://kamoamoa.eecs.northwestern.edu/)
