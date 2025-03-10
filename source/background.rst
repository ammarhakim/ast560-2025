Course Overview
---------------

Computational physics allows us to study physical systems using
computers. However, computational physics *itself* lives at the
intersection of theoretical physics, applied mathematics and computer
science. One can consider computational physics as the study of the
*physics* of discrete systems. Note this is the reverse of how one
applies computational physics, that is, uses it to study physical
systems. In this sense, computational physics has nothing to do with
the "real world" per-se but is a purely mathematical field that
studies a specific sort of problems inspired by physics. 

See `these two slides <./_static/UDS-No-Free-Lunch.pdf>`_ for a
definition of the **Ultimate Discrete Scheme** (it does not exist, or
perhaps exists in the sense of unicorns exists) and the **No Free
Lunch Principle**. These two principles will guide our development in
this course.

Vlasov-Maxwell Equations
++++++++++++++++++++++++

Vast majority of plasma physics is contained in the Vlasov-Maxwell
equations that describes the evolution of a particle distribution
:math:`f_s(t,\mathbf{x},\mathbf{v})` function in 6D phase-space. The
particles move in electromagnetic fields that come from two sources:
(i) external coils and electrodes, and (ii) fields generated by the
motion of the particles themselves. This makes the problem highly
nonlinear: the fields tell the particles how to move, and the
particle motion itself modifies the fields.

.. math::

   \frac{\partial f_s}{\partial t}
   + \nabla_\mathbf{x} \cdot (\mathbf{v}f_s)
   + \nabla_\mathbf{v} \cdot (\mathbf{a}_s f_s)
   =
   \left( \frac{\partial f_s}{\partial t} \right)_c
	
where :math:`\mathbf{a}_s =
q_s/m_s(\mathbf{E}+\mathbf{v}\times\mathbf{B})` is the acceleration
due to Lorentz force on the particle and the right-hand side describes
the effect of collisions. Of course, the electromagnetic fields are
determined from Maxwell equations

.. math::

   \epsilon_0\mu_0 \frac{\partial \mathbf{E}}{\partial t}
   - \nabla_\mathbf{x} \times \mathbf{B} &= -\mu_0
     \sum_s q_s \int_{-\infty}^{\infty} v f_s d\mathbf{v}^3 \\
   \frac{\partial \mathbf{B}}{\partial t}
   + \nabla_\mathbf{x} \times \mathbf{E} &= 0 \\
   \nabla_\mathbf{x}\cdot\mathbf{E} &=
   \frac{1}{\epsilon_0}\sum_s q_s \int_{-\infty}^{\infty} f_s d\mathbf{v}^3 \\
   \nabla_\mathbf{x}\cdot\mathbf{B} &= 0.

Suitable modifications are required to account for relativistic
effects.
   
Having written the basic equations it may appear that the field of
plasma physics is complete. However, this is far from the case. The
Vlasov-Maxwell system is a formidable system of coupled, nonlinear
equations and describes vast physics that spans an enormous range of
temporal and spatial scales. Everything from electron oscillations to
slow, resistive evolution of objects in near equilibrium is contained
within them. Hence, over the decades many approximations to the
Vlasov-Maxwell equations have been developed that are often more
tractable, allowing one to obtain reasonable results in specific
physical situations. Of course, the frontier in computational and
theoretical plasma physics remains the complete kinetic understanding
of plasma from the full Vlasov-Maxwell equations, and much of the
recent research focus has been on solving them (or asymptotic
approximations in strong magnetic fields) directly.

In this course we will look at the key modern computational techniques
to handle various problems in fluid mechanics and plasma physics. This
field remains an active area of research, and in the recent years has
undergone a renaissance of sorts. My goal will be give you a flavor of
the methods and point out key literature in this field. In particular
we will study:

- A sequence of increasingly complicated models and numerical schemes,
  focusing on understanding the properties of the model and the
  discrete schemes.

- Solving fluid equations that are obtained from taking moments of the
  Vlasov-Maxwell equations and making a closure to approximate the
  moments not evolved by the fluid equations. Here we will study the
  modern approach based on the theory of hyperbolic PDEs and Riemann
  solvers. We will also look at the special requirements of solvers
  that are required to study fusion problems.

- Directly discretizing the Vlasov-Maxwell equations as a PDE in
  6D. This is an emerging area of active research and has applications
  to study of turbulence in fusion machines and also exploring
  fundamental plasma physics in phase-space.

Through these topics we will look at the general applied mathematics
literature for solvers for ordinary differential equations (ODEs) and
partial differential equations (PDEs), with emphasis of those
techniques that are useful in plasma physics.
