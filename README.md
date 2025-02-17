# Tutorial 1

## Assignment 1

## Assignment 2

## Assignment 3

This assignment introduces the fundamental packing problem in soft matter.

## Instructions

1. **Run Simulation**
   - Execute the `in.3dlj` script on Habrok.
   - Visualise the trajectory. Can you observe any crystalline regions with the naked eye?

2. **Extract Data from Log File**
   - From the LAMMPS log file, extract the following as a function of time:
     - Temperature
     - Pressure
     - Kinetic Energy
     - Potential Energy
   - The log file is saved in a YAML format, which can be loaded into a Pandas DataFrame for easy manipulation.

3. **Beadspring Analytics**
   - Compute the radial distribution function and the mean squared displacement.
   - Refer to the following submodules for the computations:
     - `structural_properties`
     - `dynamical_properties`

4. **Run at Different Conditions**
   - Perform simulations at different temperatures and packing fractions.
   - Plot your findings to analyse the results.

## Assignment 4

## Additional Information

- Ensure you have the necessary dependencies installed for running the simulations and data analysis.
- Use the provided scripts and submodules to assist with the computations and visualisations.
- Document your observations and results thoroughly for each step.
