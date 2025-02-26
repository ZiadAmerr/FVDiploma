# UVM
Universal Verification Methodology

## Traditional test
Single test module instantiates the whole test suite, where you input stimulus using test module, the stimulus goes to the DUT

## Why SystemVerilog?
§ Constrained Randomization (exhaustive, directed, constrained random)

- Functional Coverage
    - It tells us when to stop? What we actually tested against our plan of verification

- Class (OOP)

- Assertions
    - Check properties of the design and ensure certain conditions are met

## OOP Review
Parametrized classes allow for customization of objects at compile time. We can parametrize a value, a type, multiple combinations of each.

### Extending SV classes
Inheritance allows a new class to inhreit the properties and methods from an existing class. This mechanism promotoes hierarchical organization and code reuse. The derived class can add new properties and methods or override existing ones. Original class is the base or super class


## Virtual Interface
It is a synonym for the _Façade_ desgin pattern. Instead of TB interacting with the DUT through direct manipulation of arguments, interface eases out this interaction. The virtual interface is a pointer to an actual interface.

### What UVM provides
- TB methodology - How to use SV tools to create effective testbench
Reusability
Maintainability
Scalability

- Component Hierarchy
- Message Reporting
- Factory

- Configuration Mechanism
    - Shared area for storing information
- Transaction-level Communication
    - Communication between verification components
- Verification Phases
    - ??
- Stimulus Generation
    - ??

### UVM Topology
Env instantiates components for driving, monitoring and checking

Test class configures the environment and generates the stimulus

$$
-\text{top\_module}-
$$
$$
\uparrow
$$
$$
-\text{uvm\_test}-
$$
$$
\uparrow
$$
$$
-\text{uvm\_env}-
$$
$$
\uparrow
$$
$$
-\text{uvm\_scoreboard}-
$$
$$
\uparrow\uparrow\uparrow
$$
$$
-\text{interface}-
$$
$$
\uparrow \downarrow
$$
$$
-\text{DUT}-
$$

## UVM Verification Phases

Every TB has three phases:
- Construction phase
- Run-time phase
- Cleanup phase

Phase Objection
Run phase is time consuming, and different components can consume different time. UVM provides an objection mechanism by which a component which is taking longer time to complete a task can create an objection

