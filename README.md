# From Homogeneity to Heterogeneity ,Refining stochastic simulations of gene regulation
Gene expression is regulated by RNA and DNA binding proteins (transcription factors).
These exist in limited quantities, so:
Gene expression is inherently stochastic.
To model this, we use the CME (Chemical Master Equation)
→ But analytical solutions are often not possible.
So we use:
SSA (Stochastic Simulation Algorithm) (Gillespie)
Limitation of SSA
Assumes well-mixed homogeneity (not realistic)
Does not capture spatial heterogeneity
Addressing Spatial Effects
1. Compartment-based Models
Divide system into compartments
Each compartment treated as well-mixed
2. Agent-based Models
Simulate individual molecule behavior
⚠️ Both are computationally intensive
Langevin Approach
Simplifies SSA
Works for large molecule numbers
But introduces approximations
Comparison: SSA vs Spatial SSA
Standard SSA → assumes homogeneity
Spatial SSA → includes diffusion & compartments
They produce different transcription factor dynamics, especially:
Away from steady state
In heterogeneous environments
Approximations to Spatial SSA
Quasi-Steady-State Approximation (QSSA / stQSSA)
Reduces system complexity
Introduces approximation errors
Slow-scale QSSA (slQSSA)
Works when gene copy number is low
Both SSA & spatial SSA become accurate in this regime
Simple Gene Model
Promoter Binding
DNA has binding site (BS)
�: free DNA
�: bound DNA (repressor attached)
Transcription
DNA → mRNA → protein (P)
Transcription rate depends on:
Number of available binding sites
Cases
If 2 sites active → transcription at rate �
If 1 site occupied → reduced transcription
If both occupied → transcription suppressed
Spatial SSA Concept
Divide domain into compartments of size �
Molecules diffuse between compartments
�: diffusion coefficient
Key Note
Real systems:
Have multiple binding sites
Transcription rate ∝ number of free sites
QSSA (Quasi-Steady-State Approximation)
Need for Speed
Some species:
Bind/unbind very rapidly
These are assumed to reach steady state quickly
Assumption
Fast reactions → always in equilibrium
Solve only slow dynamics
In This Model
QSSA applied to:
Number of free binding sites
Full CME is hard → but reduced CME is solvable
Two Types
1. Stochastic Low-State QSSA (slQSSA)
Focuses on binding/unbinding
Highly accurate for full model
But mathematically complex
2. Total-State QSSA (stQSSA)
Uses total variables:
Total DNA = free + bound
Simpler but less accurate in some cases
Comparison
slQSSA
stQSSA
Accurate for full model
Easier to compute
Complex math
Uses total variables
Good for binding dynamics
Works well when binding is not too tight
Stochastic QSSA & Oscillations
Can show oscillatory dynamics
Example:
If � → no average behavior
Real Cell Behavior
Oscillations arise due to:
Production & Transport
Protein produced → diffuses outward
Spatial Diffusion Delay
Delay in protein reaching DNA
Repression
Protein binds promoter → stops production
Release & Reset
Protein decreases → DNA becomes free again
Next Cycle Begins
Key Insight
Spatial delays + feedback loops → oscillations
Applications of QSSA
Alternative to:
Michaelis–Menten equations
Used for:
Simplifying complex stochastic models
Better parameter estimation
Example:
Pharmacokinetics (e.g., drug clearance)
Final Takeaways
SSA → exact but assumes homogeneity
Spatial SSA → realistic but expensive
Tau/QSSA methods → trade accuracy for speed
Best approach depends on:
i)System size
ii)Speed of reactions
iii)Importance of spatial effects

<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/a3dd59bd-ca75-4da6-b79e-f50e262143db" />
<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/046e3ae3-71ad-46c8-b7cc-bb46136bd811" />
<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/6ca3a594-91fe-4102-a83a-6c29c7d8bb17" />
<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/38da2b6c-5731-46b8-a022-b19408a85095" />



General
<img width="1161" height="690" alt="image" src="https://github.com/user-attachments/assets/461eb9ab-2f53-418a-bf1a-75c9f1e8e44c" />

slQSSA and stQSSA
<img width="1231" height="720" alt="image" src="https://github.com/user-attachments/assets/bc2bcdb0-e2d5-4105-b4df-34b3840629cb" />

tQSSA in oscialltory dynamics
<img width="1211" height="737" alt="image" src="https://github.com/user-attachments/assets/bcb0f1a4-b0fe-4417-905c-c5c05b204ca4" />
