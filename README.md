# gilliespie-algorithm types
Monte Carlo Simulation & Gillespie Algorithm
Monte Carlo Simulation
Helps us predict possible outcomes using randomness.
Think of a maze → many possible paths → randomness helps explore outcomes.
Steps:
Identify parameters of the system
Assign probability distributions (e.g., normal, uniform) to uncertain variables.
Random Sampling
Randomly draw hundreds or thousands of sample values from these distributions to build scenarios.
Run the Model
Process sample values through a deterministic mathematical model or formula to produce results.
Aggregate Results
Combine outputs to estimate probabilities.
Based on the Law of Large Numbers:
As number of samples → ∞, observed probability → true probability.
Example (Estimating π):
Ratio of circle area to square:
π ≈ 4 × (Points inside circle / Total points)
Random sampling → estimate true probability → scalable and predictable.
Gillespie Algorithm
Overview
A dynamic stochastic simulation method
Used to simulate time-dependent, discrete, random events in a system.
Key Idea
The algorithm answers:
When will the next event occur?
Which event will occur?
Mathematical Representation
Master equation:
dPt/dt=A(t)Pt
Describes how probability of being in a given state evolves over time.
Terms:
�: Column vector
→ Each entry = probability of system being in a state at time t
�: Transition rate matrix (generator matrix)
→ Defines rate of transitions between states
Why Gillespie?
Allows exact simulation of stochastic dynamics
Analytical solutions are possible only for simple systems
Complex systems (many reactions) → require simulation
Pseudo Code (Gillespie Algorithm)
Initialization
Set initial system state and concentrations
Monte Carlo Step
Randomly determine:
Time to next event
Which event occurs
Update
Move simulation time forward
Update system state
Repeat
Continue until stopping condition is met
Tau-Leaping Method
Concept
A modified version of the Gillespie method
Instead of one event at a time:
Take a time step τ
Estimate how many reactions occur within τ
Update system in one step
Trade-off
Large τ → Faster, less accurate
Small τ → More accurate, similar to Gillespie
⚠️ If τ is too small → may miss events or reduce efficiency
Pseudo Code (Tau-Leaping)
Initialize
Set initial conditions and leap size (τ)
Calculate Event Rates
For each reaction type based on system state
Monte Carlo Sampling
For each reaction, sample number of occurrences within τ
Update System
Update state based on sampled events
Repeat
Until stopping condition is reached
Problem
Fixed τ is not suitable for all systems
System dynamics may change rapidly → sensitivity to τ
Adaptive Tau-Leaping
Idea
Use adaptive τ instead of fixed τ
Solution
Dynamically adjust τ based on system behavior:
Faster changes → smaller τ
Slower changes → larger τ
Steps:
Initialize system
Calculate reaction rates �
Compute auxiliary variables:
Mean:
Choose τ:
Ensures stability and accuracy
Prevents large errors during rapid system changes
Key Insight
Adaptive tau-leaping improves:
Accuracy
Efficiency
Especially useful for systems where populations fluctuate quickly
If you want, I can turn this into:
exam notes (very concise),
flowcharts,
or a step-by-step numerical example (like solving one Gillespie iteration).


Reference : https://lewiscoleblog.com/gillespie-algorithm
<img width="1200" height="1600" alt="WhatsApp Image 2026-05-19 at 11 25 44" src="https://github.com/user-attachments/assets/a4aa7e99-e623-4232-9f2d-5a4de4864b8d" />
<img width="1200" height="1600" alt="WhatsApp Image 2026-05-19 at 11 25 44 (1)" src="https://github.com/user-attachments/assets/6993bcdc-ab55-43ef-bb11-ecf07cad8b73" />
<img width="1200" height="1600" alt="WhatsApp Image 2026-05-19 at 11 25 44 (2)" src="https://github.com/user-attachments/assets/47676370-5fd1-4840-9621-9efe9a24cb78" />


