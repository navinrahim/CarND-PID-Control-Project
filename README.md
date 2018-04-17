# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---
The goal of the project is to drive the car in the simulator using the PID controller. The PID controller is used to adjust the steering angle, so that the car in the simulator stays in the drivable portion of the road.

## Reflection

### 1. Effect of each of the P, I, D components in the implementation.

**Effect of P :** The P component is used to control how fast the values should converge to the actual value. In this project, it means how fast the car adjusts itself to be ideally in the middle of the road. As the P component increases, the system tends to converge to the actual values faster, but may result in overshooting which causes a lot of oscillations around the actual value. When running the simulator, this causes the car to wobble in the track.

**Effect of I :** The I component is used to make the convergence of the values to the actual values faster. For cars, this is used when there is a drift present and the car consistently stays away from the ideal position. The I term decides how much of the previous consolidated error should be used to faster move towards the actual value.

**Effect of D :** The D componenet is used to reduce the overshooting that happens when trying to converge to the actual values and reach the stable point faster. It makes the change of errors to converge to zero faster, thus helping to reduce the overshooting effect.

### 2. Description of how the final hyperparameters were chosen.

I started with a `Kp` value of 1.0 and the `Kd` and `Ki` values to 0s. This caused the car to wobble a lot around the track and eventually went out of the track. So, I reduced the `Kp` value to 0.5. This resulted in lesser wobbling. Inorder to smoothen the car's oscillations, I increased the `Kd` value to 0.5. This smoothened the car's motion, but a bit of oscillations were visible. So, I decreased the `Kp` value to 0.4 which resulted in lesser wobbling around.

The value of `Ki` was not changed from 0 as there was no biasing due to drift present which cause the car to stay away from the middle of the road. The final values of `Kp`, `Ki` and `Kd` used are 0.4, 0 and 0.5 respectively.


