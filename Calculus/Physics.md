# Newtonian Physics

## Variables and Notation

- $t$ = time elapsed
    - Note that $\Delta t = t$ if we set the initial time equal to 0

- $v_0$ = initial velocity
    - Can also be written as $v(0)$

- $v$ = final velocity at time $t$
    - Can also be written as $v(t)$

- $a$ = constant acceleration
    - Can also be written as $a(t)$

- $x$ = position
    - Can also be written as $x(t)$

- $s$ = displacement (a.k.a change in position)
    - $s = x(t) - x_0$

## Fundamental Relationships

$$v(t) = \frac{dx}{dt}$$

$$a(t) = \frac{dv}{dt} = \frac{d^2x}{dt^2}$$

## Three Equations of Motion

**First Equation: Velocity-Time Relationship:**
$$v = v_0 + at$$

**Second Equation: Displacement-Time Relationship:**
$$s = v_0t + \frac{1}{2}at^2$$

**Third Equation: Velocity-Displacement Relationship:**
$$v^2 = v_0^2 + 2as$$

## Constant Velocity Model

When acceleration is zero ($a = 0$), we have the special case of constant velocity motion. In this model, an object maintains the same speed and direction throughout its journey. This is the simplest form of motion and represents the state of an object when no net force acts upon it.

### Simplified Equations for Constant Velocity

When $a = 0$, the three equations of motion simplify to:

1. First equation: $$v = v_0$$
   The final velocity equals the initial velocity; velocity remains constant.

2. Second equation: $$s = v_0t$$
   Displacement is directly proportional to time, with the constant of proportionality being the velocity.

3. Third equation: $$v^2 = v_0^2$$
   This simply confirms that the velocity is unchanged.

## Relationship to Position

Displacement ($s$) is the change in position, representing how far an object has moved from its initial position ($x_0$):

$$s = x(t) - x_0$$

Therefore, position as a function of time can be derived from the displacement equation:

$$x(t) = x_0 + s = x_0 + v_0t + \frac{1}{2}at^2$$

This equation gives the complete position of an object at any time $t$, assuming constant acceleration.

### Position in the Constant Velocity Model

In the constant velocity model (where $a = 0$), the position equation simplifies to:

$$x(t) = x_0 + v_0t$$

This is a linear function of time, representing motion along a straight line with position changing at a constant rate.