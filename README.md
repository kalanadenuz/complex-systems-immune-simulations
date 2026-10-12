# Complex Systems & Agent Technologies: Multi-Agent Immune Simulations

This repository contains two computational biology agent-based models developed in NetLogo (2D and 3D) on Ubuntu Linux, simulating decentralized search, stigmergy, cellular contagion, and predator-prey swarm dynamics.

---

## Repository Structure

```text
├── project1-3d-lymph-node-swarm/
│   ├── Model1_3D_LymphNode_Swarm.nlogo3d
│   ├── README.md
│
├── project2-2d-viral-plaque-dynamics/
│   ├── Model2_2D_Viral_Propagation.nlogo
│   ├── README.md
│
└── README.md

```

---

## Project 1: 3D Lymph Node Swarm Intelligence & Stigmergic Chemotaxis

### Overview

Simulates the search behavior of naïve T-cells seeking rare Dendritic Cells (DCs) presenting foreign antigens within a continuous 3D toroidal volume.

### Core Features

* **Stigmergy & Diffusion:** Dendritic cells act as stationary signaling hubs that continuously emit chemokines into 3D voxels. The chemical field diffuses across cubic neighborhoods and decays exponentially over time.
* **Chemotactic Guidance:** T-cells evaluate local 3D gradients and bias their heading toward higher concentrations rather than relying solely on Brownian random walks.
* **Cognitive State Machine:**
* **Searching (Green):** Chemotactic gradient ascent.
* **Synapse Bound (Blue):** Physical link formed within 2 patches of a DC, pausing movement for 3 minutes for antigen transfer.
* **Primed Effector (Yellow):** Differentiates after cumulative exposure reaches 6 minutes, accelerates, and egresses from the volume.



### Environment & Execution

* **Platform:** NetLogo 3D
* **Dimensions:** min-pxcor: -16 to max-pxcor: 16 (centered origin, wrapped across x, y, and z)
* **Time Step:** dt = 0.5 min per tick

---

## Project 2: 2D Viral Propagation & CTL Predator-Prey Dynamics

### Overview

Models the spatial spread of a viral infection across an epithelial cell monolayer alongside adaptive immune clearance by Cytotoxic T Lymphocytes (CTLs).

### Core Features

* **Cellular Automaton Monolayer:** Host patches transition through four distinct phases:
* Uninfected (White) -> Latent Eclipse Phase (Green) -> Actively Infectious (Red) -> Apoptotic / Dead (Black).


* **Dual-Layer Transmission:**
* **Local Contagion:** Direct cell-to-cell spread across adjacent Moore neighbors.
* **Convective Jumps:** Virions shed into the extracellular fluid stochastically initiate separate infection foci across the dish.


* **Adaptive Immune Swarm:** Naïve CTLs patrol the tissue. Contact with infected patches triggers activation into killer effectors, immediate target neutralization, and density-dependent clonal division every 3 kills (capped by replicative senescence).

### Environment & Execution

* **Platform:** NetLogo (Standard 2D)
* **Dimensions:** min-pxcor: -40 to max-pxcor: 40 (wrapped horizontally and vertically)
* **Time Step:** dt = 0.1 hours (6 minutes) per tick

---

## How to Run

1. Clone this repository:
```bash
git clone https://github.com/kalanadenuz/complex-systems-immune-simulations.git
cd complex-systems-immune-simulations

```


2. Open NetLogo:
* For **Project 1**, launch **NetLogo 3D** and open `project1-3d-lymph-node-swarm/Model1_3D_LymphNode_Swarm.nlogo3d`.
* For **Project 2**, launch **NetLogo 2D** and open `project2-2d-viral-plaque-dynamics/Model2_2D_Viral_Propagation.nlogo`.


3. Click `setup` to initialize the environment and agents, then click `go` to run the simulation.

---

## Video Presentations

* [Project 1: 3D Lymph Node Simulation](https://www.youtube.com/watch?v=g_ZafEaabaY)
* [Project 2: 2D Viral Propagation Simulation](https://www.youtube.com/watch?v=i9zZtG-7oIc)

```

```