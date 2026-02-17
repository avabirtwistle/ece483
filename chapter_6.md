# Optical Flow
- Apparent 2D motion perceived from image changes by tracking how pixel brightness patterns shift between frame
- Inspired by human vision tracking motion by following the brightness pattern changes over time
- Not always the same as true 2D motion, ex. rotating the light source around a stationary object will be perceived as motion in optical flow

# Motion Estimation
Motion estimation is a used in video processing to determine the dusplacement of image points/objects between different frames in a video sequence
- Computers perceive motion as temporal changes (variation in image intensity) at certain points over time

## Use Cases 
### Video compression
- Instead of coding or saving every frame as an independent image, temporal prediction (specifically motion-compensated prediction) is used to predict a current frame from a previously coded reference frame
- For each block or region, a motion vector (displacement vector) is calculated to identify its matching location in the reference frame
- After, the prediction error—which (difference between the actual frame and its prediction) is calculated
- Only motion vectors and the prediction error are stored/transmitted saving space and bandwidth
  
## Regularization (smoothness constraints)
 Assume motion is smooth neighboring pixels should have similar motion.
How it works:
- You still have the problem: 1 equation, 2 unknowns per pixel
- But now add a rule: "A pixel's motion should be close to its neighbors' motion"
- creates additional constraints that help solve the problem

$$ E(v(x)) = \Sigma_{x \in \Lambda} \left( \frac{\partial \psi}{\partial s}v_x+ \frac{\partial \psi}{\partial y} + \frac{\partial \psi}{\partial t} \right)^2 + w_s(||\nabla v_x||^2+||\nabla v_y||^2) $$
Flow based criterion:
