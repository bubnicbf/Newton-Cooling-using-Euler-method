# Euler-method
Euler's method numerically approximates solutions of first-order ordinary differential equations with a given initial value.

Euler's method numerically approximates solutions of first-order ordinary differential equations (ODEs) with a given initial value. It is an explicit method for solving initial value problems (IVPs), as described in the wikipedia page. The ODE has to be provided in the following form:

$$ 
\frac{dy(t)}{dt} = f(t,y(t)) 
$$

with an initial value

$$
y(t0) = y0
$$

To get a numeric solution, we replace the derivative on the LHS with a finite difference approximation:

$$
\frac{dy(t)}{dt}  \approx \frac{y(t+h)-y(t)}{h}
$$

then solve for $y(t + h)$:

$$
y(t+h) \approx y(t) + h \, \frac{dy(t)}{dt}
$$

which is the same as

$$
y(t+h) \approx y(t) + h \, f(t,y(t))
$$

The iterative solution rule is then:

$$
y_{n+1} = y_n + h \, f(t_n, y_n)
$$

$h$ is the step size, the most relevant parameter for accuracy of the solution. A smaller step size increases accuracy but also the computation cost, so it has always has to be hand-picked according to the problem at hand.

####Example: Newton's Cooling Law
Newton's cooling law describes how an object of initial temperature $T(t0) = T0$ cools down in an environment of temperature $T_R$:

$$
\frac{dT(t)}{dt} = -k \, \Delta T
$$

or

$$
\frac{dT(t)}{dt} = -k \, (T(t) - T_R)
$$

It says that the cooling rate $\frac{dT(t)}{dt}$ of the object is proportional to the current temperature difference $ΔT = (T(t) − T_R)$ to the surrounding environment.

The analytical solution, which we will compare to the numerical approximation, is

$$
T(t) = T_R + (T_0 - T_R) \; e^{-k t}
$$
