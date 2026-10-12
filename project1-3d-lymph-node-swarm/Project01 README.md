# Project 1: 3D Lymph Node Swarm Intelligence & Stigmergic Chemotaxis

An agent-based simulation modeling decentralized lymphocyte search and antigen discovery in a continuous 3D toroidal lymph node environment using NetLogo 3D.

## Scientific Overview
In secondary lymphoid tissue, naive T-cells must efficiently locate rare antigen-bearing Dendritic Cells (DCs). Rather than relying on simple Brownian motion, this model demonstrates swarm intelligence through environmental stigmergy:
- **Signaling Beacons (DCs):** Two static hubs continuously emit signaling chemokines into the surrounding 3D voxels.
- **Environmental Stigmergy:** The chemokine field diffuses across cubic 3D neighborhoods and degrades enzymatically over time.
- **Chemotactic Guidance:** Naive T-cells sample local gradients to steer toward higher chemical concentrations.
- **Cognitive State Architecture:**
  - `searching` (Green): Executes gradient-biased 3D exploration.
  - `bound` (Blue with Red Link): Forms a 3-minute physical immunological synapse upon entering a 2-patch radius of a DC.
  - `activated` (Yellow): Reaches the 6.0-minute cumulative exposure threshold, breaks the synapse, and accelerates outward to exit the node.

## Simulation Specifications
- **Platform:** NetLogo 3D
- **Dimensions:** `min-pxcor = -16`, `max-pxcor = 16`, `min-pycor = -16`, `max-pycor = 16`, `min-pzcor = -16`, `max-pzcor = 16` (Origin centered, wrapped across all axes)
- **Patch Scale ($ds$):** 8 um per patch
- **Temporal Step ($dt$):** 0.5 minutes per tick

## Parameters & Interface Controls
- `tcell-count` (Slider: 50 - 300, Default: 100): Initial population of naive T-cells.
- `chemotaxis-bias` (Slider: 0.0 - 1.0, Default: 0.70): Probability of choosing gradient ascent over random exploratory walks.
- `chemokine-emission` (Slider: 1.0 - 15.0, Default: 8.0): Emission rate per step from dendritic hubs.

## Live Analytical Plots
1. **Chemokine Concentration:** Real-time peak chemokine signal across the 3D volume, illustrating dynamic steady-state equilibrium.
2. **Swarm Dynamics:** Compares cumulative immunological synapses against the total count of primed effector T-cells.

## How to Run
1. Open NetLogo 3D.
2. Load `Model1_3D_LymphNode_Swarm.nlogo3d`.
3. Set the desired parameters using the interface sliders.
4. Click `setup` to initialize the volume, DCs, and T-cell agents.
5. Click `go` to start execution. The model halts automatically once 100% of the T-cell population reaches the primed effector state.