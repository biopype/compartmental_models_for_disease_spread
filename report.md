# Compartmental modeling for disease spread using ODEs and Partial derivatives
## Introduction
Understanding the dynamics of disease spread in epidemiology is important for policymakers and researchers to:
- Plan and execute resource allocation.
- Predict trends and assess the effect of treatments.
- Make meaningful conclusions based on collected data to promote disease control.

## Compartmental Models
Mathematical models, such as **Susceptible-Infected-Recovered (SIR)** and **Susceptible-Exposed-Infected-Recovered (SEIR)**, play a pivotal role in mapping these dynamics. These models:
- Are based on ordinary differential equations (ODEs) to simulate population changes over time.
- Utilize partial derivatives to assess the effects of various parameters, such as vaccination and social distancing, on population changes.

This report focuses on the development of SIR and SEIR models using ODEs and partial derivatives to understand the effect of parameters on the population over time.

### Aim
To simulate and analyze the dynamics of disease spread using the SIR and SEIR models, and to understand the role of ODEs in population modeling and partial derivatives in parameter sensitivity.

### Objectives
1. Develop SIR and SEIR models using ODEs to represent transitions between compartments (susceptible, exposed, infected, recovered).
2. Use partial derivatives to explore how changes in transmission and recovery rates influence disease progression.
3. Simulate and visualize the results to understand disease dynamics and inform potential interventions.

## Methodology

### Ordinary Differential Equations in the SIR Model
The SIR model divides the population into three compartments:
- **Susceptible (S):** Individuals who can contract the disease.
- **Infected (I):** Individuals who have contracted and can spread the disease.
- **Recovered (R):** Individuals who have recovered and are no longer infectious.

The dynamics are governed by the following ODEs:
![image](https://github.com/user-attachments/assets/2d9a10fa-7164-4ff9-bf98-ba1a20b64e15)

- **β:** Transmission rate (rate of contact between susceptible and infected individuals).
- **γ:** Recovery rate (the rate at which infected individuals recover).

For **SEIR**, another compartment (**Exposed (E)**) is added. The equations describe how each compartment changes over time based on disease parameters.

### Partial Derivatives in Sensitivity Analysis
Partial derivatives are used to determine how sensitive the model outputs (e.g., dS/dt, dI/dt) are to changes in key parameters (**β, γ**):
- For instance, the partial derivative of **dS/dt** with respect to **β** is:
![image](https://github.com/user-attachments/assets/89836451-68a4-4be5-bd49-665b72741af4)

- An increase in **β** (e.g., a more contagious disease) increases the rate at which susceptible individuals are infected.

### Steps for Simulation and Analysis
1. **Formulate the Model:**
   - Define the ODEs for the SIR model using a Python library like `scipy.integrate.odeint`.
   - Define parameters (**β, γ**) and initial conditions.
2. **Solve the ODEs:**
   - Numerically solve the equations over a specified time period to simulate disease progression.
3. **Analyze Partial Derivatives:**
   - Use symbolic computation (e.g., `sympy`) to calculate partial derivatives of **dS/dt** and **dI/dt** with respect to **β** and **γ**.
   - Interpret these results to understand how changes in transmission or recovery rates influence disease spread.
4. **Visualize Results:**
   - Plot **S(t)**, **I(t)**, and **R(t)** over time to visualize disease dynamics.
   - Explore sensitivity by visualizing how **∂dS/∂β** changes with **S** and **I**.

## Interpreting the SIR Dynamics
![image](https://github.com/user-attachments/assets/f141de0e-b126-49f8-8048-044055465e93)


### 1. Initial Phase:
- Most of the population is susceptible, and infections are low.
- Disease spreads as infected individuals contact susceptible ones.

### 2. Exponential Growth:
- As infections rise, more people become exposed.
- Recovery rates are initially slower than infection rates, leading to a rapid increase in infections.

### 3. Peak Infection:
- The infected curve reaches its maximum.
- This is when the disease spreads fastest and puts the highest strain on resources like healthcare.

### 4. Decline and Stabilization:
- The infection rate drops as more people recover and the susceptible pool shrinks.
- Eventually, the recovered population stabilizes, representing herd immunity.

## Interpreting the SEIR Dynamics
![image](https://github.com/user-attachments/assets/4eb8c04c-11e8-403e-afd9-d7979fc021e3)


### 1. Initial Phase:
- Susceptible individuals dominate.
- A small number of infections cause the exposed compartment to grow.

### 2. Epidemic Growth:
- The exposed and infected compartments rise as the disease spreads through the population.
- Susceptible individuals decrease rapidly.

### 3. Peak Infection:
- Infected individuals reach a maximum, indicating the worst phase of the outbreak.
- This corresponds to a rapid rise in recoveries.

### 4. Post-Epidemic Phase:
- As infections wane, recoveries dominate.
- The susceptible population stabilizes, representing individuals who avoided exposure.

## Impact of vaccination on disease spread
![image](https://github.com/user-attachments/assets/9e307277-492d-44cb-8e98-5b6ac93bf03f)

## Plotting the partial derivative
![image](https://github.com/user-attachments/assets/f05cb7b0-2e48-4fe0-9e6b-5207b79753ac)

## Plotting the effect on partial derivative with varying **I** or **β**
![image](https://github.com/user-attachments/assets/4aeec8c4-b969-4042-8eba-6405504f329a)




## Results

### 1. Simulation of Disease Spread:
- Graphs of **S(t)**, **I(t)**, and **R(t)** showed typical disease progression:
  - Rapid initial increase in infected individuals.
  - Peak infection followed by a decline as more individuals recover.
  - Steady-state where most of the population is recovered.

### 2. Sensitivity Analysis:
- Partial derivatives demonstrated:
  - Higher **β** leads to a faster decline in **S** (susceptible population).
  - Lower **γ** extends the duration of infection peaks, delaying recovery.

### 3. Visualization:
- Sensitivity plots revealed how the rate of change depends on population and parameter values.

## Importance in Epidemiology

### 1. **Predictive Modeling:**
   - ODEs allow for accurate predictions of disease spread, which helps in public health planning.
### 2. **Understanding Parameter Influence:**
   - Partial derivatives highlight critical parameters like transmission and recovery rates, helping to design targeted interventions.
### 3. **Evaluating Interventions:**
   - Simulations can model the effects of vaccination, quarantine, or social distancing by altering **β** or **γ**.

## Conclusion
The SIR and SEIR model, formulated using ODEs and analyzed with partial derivatives, provides a robust framework for understanding infectious disease dynamics. It highlights the interplay between disease parameters and population transitions. This offers valuable insights for epidemiology and public health interventions.
