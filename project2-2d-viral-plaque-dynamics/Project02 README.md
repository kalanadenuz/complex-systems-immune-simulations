# Project 2: 2D Viral Propagation & CTL Predator-Prey Dynamics

A hybrid agent-based simulation modeling spatial viral plaque transmission across a confluent host cell monolayer coupled with predatory Cytotoxic T-Lymphocyte (CTL) clearance using NetLogo 2D.

## Scientific Overview
This model couples a 4-state Cellular Automaton representing host tissue with mobile immune agents executing targeted pursuit and proliferation:
- **Host Monolayer (Patches):** Represents an epithelial cell sheet undergoing discrete pathological state transitions:
  - `uninfected` (White): Healthy, susceptible tissue.
  - `latent` (Green): Eclipse phase; intracellular virion assembly without shedding (mean duration: 6.0 hours).
  - `infectious` (Red): Active viral release to neighboring tissue and shared fluid (mean duration: 12.0 hours).
  - `dead` (Black): Apoptosis or lysis triggered by infection or CTL contact.
- **Multi-Scale Transmission:**
  - *Local Contagion:* Direct contact-mediated infection across adjacent Moore neighbors.
  - *Convective Fluid Spread:* Excess virion accumulation in extracellular fluid triggers stochastic non-local infection jumps.
- **Adaptive Immune Swarm (CTLs):**
  - *Surveillance:* Naive CTLs (Cyan) patrol the monolayer.
  - *Target Engagement:* Contact with infected patches triggers differentiation into cytotoxic effectors (Magenta) and immediate target neutralization.
  - *Clonal Proliferation:* Effectors detect infectious cells within a 4-patch sensory radius and undergo mitosis (`hatch 1`) every 3 kills, subject to a finite division cap modeling replicative senescence.

## Simulation Specifications
- **Platform:** NetLogo (Standard 2D)
- **Dimensions:** `min-pxcor = -40`, `max-pxcor = 40`, `min-pycor = -40`, `max-pycor = 40` (Origin centered, wrapped horizontally and vertically)
- **Temporal Step ($dt$):** 0.1 hours (6.0 minutes) per tick

## Parameters & Interface Controls
- `pfu` (Slider: 1 - 25, Default: 5): Initial Plaque Forming Units seeded on the monolayer.
- `transmission-rate` (Slider: 0.05 - 0.50, Default: 0.20): Probability of local viral transmission per step.
- `initial-ctls` (Slider: 1 - 20, Default: 8): Initial sentinel pool of surveillance CTL agents.

## Live Analytical Plots
1. **Cell Culture States:** Tracks populations of Uninfected, Latent, Infectious, and Dead patches over time.
2. **Immune Swarm Dynamics:** Tracks the transition of Naive CTLs into an expanding population of activated Effector CTLs.

## How to Run
1. Open standard NetLogo (2D).
2. Load `Model2_2D_Viral_Propagation.nlogo`.
3. Set the desired parameters using the interface sliders.
4. Click `setup` to initialize the monolayer, viral seed foci, and surveillance CTLs.
5. Click `go` to observe the spatial plaque dynamics, immune swarming, and real-time population plots.