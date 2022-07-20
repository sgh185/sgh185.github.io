---
layout: archive
title: "RipTide (More Details)"
permalink: /riptide/
author_profile: true
---

{% include base_path %}

---

## Control-Flow Paradigm and ISA

RipTide employs a <em>steering-based</em> control-flow paradigm (Φ<sup>-1</sup>) that saves energy. Other mechanisms
to implement control-flow include predication and selection (Φ). However, predication can waste energy by frequent
masking operations and selection wastes energy by perform both true and false sides of a branch before proceding.

Steering-based control-flow minimizes energy because values operations are gated and performed only when it is 
determined which side to execute (true and false). Values are then only sent where they are actually needed. These
operators (and others) are described in detail in the figures below.

Steering is implemented with the <em>steer</em> operators (in true and false flavors) and the <em>carry</em> operator.

Additionally, RipTide's ISA includes arithmetic, memory, synchonization, and other operators (see table below).



## Streams

RipTide's compiler identifies affine loop-governing induction variables (LGIVs) in LLVM IR and tracks them into the dataflow graph (DFG)
representation. At this level, the subgraph of operators that represent the LGIV in the DFG are fused into a stream operator, which
performs an LGIV's functionality in a single operator and fires a new value every cycle at runtime. See the "Optimized Dataflow Graph"
in the compiler pipeline diagram above.

## Memory Ordering

## Microarchitecture

## Running a DNN on RipTide

## Link 
![image info](https://souradipghosh.com/images/frame.png)
