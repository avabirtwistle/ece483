

## Regularization (smoothness constraints)
 Assume motion is smooth neighboring pixels should have similar motion.
How it works:
- You still have the problem: 1 equation, 2 unknowns per pixel
- But now add a rule: "A pixel's motion should be close to its neighbors' motion"
- creates additional constraints that help solve the problem

$$ E(v(x)) = \Sigma_{x \in \Lambda} \left( \frac{\partial \psi}{\partial s}v_x+ \frac{\partial \psi}{\partial y} + \frac{\partial \psi}{\partial t} \right)^2 + w_s(||\nabla v_x||^2+||\nabla v_y||^2) $$
Flow based criterion:
