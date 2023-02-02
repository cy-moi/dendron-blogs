---
id: isi9qi80jvtfqv94g6cmv93
title: Universal Particles
desc: ''
updated: 1675371902367
created: 1675370016654
---

Basically, it is "a unified solver capable of simulating gases, liquids, deformable solids, rigid bodies, and cloth, interacting with one another in real-time."

### PBD - [Position Based Dynamics](https://matthias-research.github.io/pages/publications/posBasedDyn.pdf)
> Typically positions are updated after each constraint is processed, and after a number of iterations a change in velocity is computed according to the total constraint delta: delta_x = delta_x/delta_t.

### Rigid Body - [Rigid Shape matching](https://matthias-research.github.io/pages/publications/orientedParticles.pdf)

> Shapes are created by first performing solid voxelization of a closed triangle mesh and placing particles at occupied cells interior to the shape. 

> Assign all particles in the shape the same phase-identifier, disable collision between them, and add a shape-matching constraint to the system.

### SDF - Signed Distance Field 
> Sample the field function onto each particle belonging to a rigid shape. 

> Re-use all the machinery of the particle-particle collision detection to resolve deeper overlaps between shapes. 

> detect overlaps between particles with distance $|xi − xj | < r$. As the contact normal we choose the SDF gradient corresponding to the minimum translation distance, $d = min(|φi|, |φj |)$.

$φ$ is the magnitude of the SDF.

