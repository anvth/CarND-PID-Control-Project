The PID Components
===================

1. The "P" in the PID controller stands for Proportional, which means, the car will steer proportinally to the Cross Track Error or CTE. CTE is essentially how far the car is from a reference line, the middle of the road in this case. For example, if the car is to the right of the reference line then it has to steer to the left and the steer angle depends on how far the car to the right of the reference line. Setting the co-efficient to a higer value means that the car will always overshoot the reference and keep oscillating. A very low co-efficient would mean that the car takes a lot of time to correct itself and fails to stay on the expected path when the road curves.

2. The "I" in the PID controller stands for Integral and this holds the sum of all the CTEs till that point in time. If, for example, the been to the left of the reference line for awhile, then too many negative CTEs would drive up the value of co-efficient which causes the car to move towards the middle. If the co-efficient is too high, the car tends to have quicker oscillations and thereby not reaching higer speeds. A very low value means that the car would drift to one side or other of the lane for longer periods of time.

3. The "D" in the PID controller stands for Derivate and it holds the change in CTE from one step to next. This co-efficient can be used in following ways:
* If the derivative is quickly changing then the car correct itself quickly(high steering angle)
* If the car is moving away from the reference line, this will cause the steering to get larger (as the derivative sign will match the proportional sign)
* If the car is moving towards the reference line (meaning the derivative value will be negative), the car's steering angle will get smoothed out.
This leads to a more smoother driving experience.

Finding the right Coefficients
===============================

The final values were determined by manual tuning. I tried lowering and raising values in conjunction with each other as well as tuning each individually. Two key observations I made were:
1. The resulting steering angles were too high when I raised the values in conjunction. This lead to lot of oscillations and crashes if the speed was high.
2. Lowering all of them together meant the car struggled on larger curves(not turning enough) and shot off the track.

The ratio of the coefficients that I chose are (0.15, 0.004, 2.5).
