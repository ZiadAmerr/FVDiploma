# _Formal Verification Pt. II_

Formal verification is converting the data inside the design into a mathematical form.

Usage: Functional Safety, Equivalence Checking, and Property Verification.


## Agenda
- Automated Reasoning and applications
- Why Formal verification?
- Formal: How to start?
- Demo
- Formal Verification Applications
- Property Checking
- Push-button apps
- User-specs apps
- Known standard apps

## Automated Reasoning and Applications
Course on Coursera for automated reasoning, good to go for initial start.
Print the maximum amount of posters in the minimum amount of area (low cost, high efficiency)

**Sudoku** has constraints -- and an end-goal (used for mathematical optimization)

$\rightarrow$ Satisfiability

## Why Formal verification
Testing 32-bit full-adders should be $2^{32} \times 2^{32}=585 \text{years}$

There is no guarantee that you'll cover everything in regular verification.

In **Formal Verification**, you mathematically prove that your design satisfies the required specifications.

When is Formal Verification and Simulation is not enough?
- Design suffered a major bug due to insufficient covertage of corner cases during sumulation testing
- Real flows in simulation, but you want to run the verification quickly (FoV is quick!)
- No need for rerunning simulation for minor code changes and solid additions (FoV is very good in small modules with small search spaces)
- Very close to production, but verification engineers keep on finding bugs, confidence is lost. Randomized simulations are just not providing proper coverage (they do not cover the code well)

### Discussion
We'll talk about formal control blocks (Control Points & Constraints). It tries to dissatisfy the system by breaking the control points.

Can be used in Formal Verification is called Synthesizable.

The output is either a **mathematical proof** or a **counter-example**.

### Types of Properties:
- Safety
- Vacuity/Implication (Make sure initial state is handled)
    - Vacuity means adding a clean condition (something satisfies another thing)
- Liveness property $\rightarrow$ fairness assumption
- Witness/Cover/Reachability property


## How do you start?
Specs $\rightarrow$ System Developer $\rightarrow$ Mathametical Model $\rightarrow$ Specs*\
Specs $\rightarrow$ Verification Engineer $\rightarrow$ Mathematical Model $\rightarrow$ Specs*

Comparison of Specs is done by **Formal Analysis**.


## Formal Verification Applications
- Property Checking
- Push Button
- Assertion generation on user-given standards
- Assertion generation on known standards

### Questa Verify Property
- Synthesizable RTL
- Constraints (SVA Assumes)
- Targets (SVA Asserts, Covers)
- Init Sequence

$\uparrow\uparrow$ All of the previous go to $\downarrow\downarrow$
- Proofs
- Counter examples
- Sanity & Witness Waveforms
- Formal Coverage


### Questa Icons
- $\mathcal{P}$: Proven
- $\mathcal{V}$: Vacuious
- $\mathcal{U}$: unprovable
- $\mathcal{F}$: Firing
- $\mathcal{C}$: Covered (counter example)
- $\mathcal{I}$: Inconclusive

### Design Setup
1. Compile RTL
1. Compile Assertions
1. Setup Clock/Reset/Constant
1. Setup Initial State
