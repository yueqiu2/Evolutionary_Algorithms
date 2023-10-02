## 1.CMA-ES in Reinforcement Learning for CSTR Control Problem
- **Aiming to control temperature and concentration in CSTR, by controlling cooling jacket temperature**
- **Reinforcement learning, using CMA-ES to optimize the policy net**
- Concentration set point: 0.8 to 0.9
- Reactor temperature set point: 330 to 320
- Decision variable: Cooling jacket temperature

#### Trainning Plot

<img width="807" alt="Screenshot 2023-10-02 at 02 55 52" src="https://github.com/yueqiu2/Machine_Learning_Code/assets/146023548/a916bdb9-6a9f-4f11-81ec-db67dbcfeff0">

#### Best Policy

<img width="782" alt="Screenshot 2023-10-02 at 02 55 19" src="https://github.com/yueqiu2/Machine_Learning_Code/assets/146023548/426e1c54-a516-4ba4-85b4-843698af5c7b">

## 2.Optimization Problem Using Gradiant Descent with Nesterov Momention + Bayesian Optimization
- Derivative-free optimization
- Challenge: (1) function evaluation budgets; (2) high dimensionality; (3)non-convexity
- Low dimensionality case: 50 budgets, with 30 for BO, and 20 for gradient descent with Nesterov momentom
- High dimensionality case: all budgets for gradient descent with Nesterov momentom
- **Beat all 3 benchmarks (Nelder-Mead, Powell, COBYLA) in all test functions**

## 3.CO2 Property Prediction with Neural Network
### Temperature + density to predict pressure
<img width="400" alt="Screenshot 2023-10-02 at 03 43 25" src="https://github.com/yueqiu2/Machine_Learning_Code/assets/146023548/5ea46c5f-ee7e-465b-96d7-a7b28cb3f341">

### Temperature + density to predict compressibility (Z=P/ρRT)
<img width="385" alt="Screenshot 2023-10-02 at 03 43 11" src="https://github.com/yueqiu2/Machine_Learning_Code/assets/146023548/fe5d2cdb-17d7-4658-8f57-590a8290eea1">
- Better fit with compressibility

### Prediction of critical density
<img width="429" alt="Screenshot 2023-10-02 at 03 45 21" src="https://github.com/yueqiu2/Machine_Learning_Code/assets/146023548/35ce0c2d-e958-444e-8bac-e9dbb5d93e35">


At the critical point, only one phase exists. The heat of vaporization is zero. There is a stationary inflection point in the constant-temperature line on a P-V diagram. At the critical point exists a mathematical relationship:

(Note: $T_{c}$ refers to critical temperature)
<img width="119" alt="Screenshot 2023-10-02 at 03 55 03" src="https://github.com/yueqiu2/Machine_Learning_Code/assets/146023548/fd412847-beff-4302-a9e6-7349967bc7ab">

We fit the liquid phase density and the gas phase density at a certain pressure in the phase envelope through the neural network, and then combine the two curves of density variation with pressure to finally find the point of minimum density variation, which is the critical point, and the pressure corresponding to the critical point is the critical pressure.

