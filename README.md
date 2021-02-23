# Kalman-Filter
1D and 2D representation of vehicle tracking using Kalman Filter

## 1D-Kalman-Filter 
Kalman Filter, which is an algorithm that uses noisy sensor measurements (and Bayes' Rule) to produce reliable estimates of unknown quantities (e.g. like where a vehicle is likely to be in 3 seconds) , represents a mathematical way to infer velocity from only a set of measured locations. Using Kalman Filter, we can estimates where future locations might be and the velocity of an object from intial parameters like positions and uncertainty.

### Objective 
In order to actually implement a Kalman Filter in a 2D or 3D world (or "state space" in the language of robotics) this 1D Kalman Filter can show the basic idea  how to keep track of robot motion and "state" (robot of a self-driving-car).

### Motion Models and State
A mathematical representation of motion: a motion model represents the position and motion of an object (an object's state). 

### Step 

1. [Gaussian Calculation](/1D-Kalman-Filter/1.%20Gaussian%20Calculations.ipynb) 
Gaussians are exponential function characterized by a given mean, which defines the location of the peak of a Gaussian curve, ad a variance which defines the width/spread of the curve. The variance is also a measure of Gaussian spread and a measure of certainty. To find the location of a car with the most certainty, we can apply a Gaussian whose mean is the location of the car and with the smallest uncertainty/spread. 
2. [Mean and Variance](/1D-Kalman-Filter/2.%20New%20Mean%20and%20Variance.ipynb)
After applying Gaussian, motion needs to be updated .This step is called the parameter or measurement update because it is the update that happens when an initial belief (represented by the Gaussian) is merged with a new piece of information, a measurement with some uncertainty (another Gaussian). By the charateristics of Gaussians, a motion update is just an addition between parameters; the new mean will be the old mean + the motion mean; same with the new variance. 
3. [Prediction](/1D-Kalman-Filter/3.%20Predict%20Function.ipynb)
After performing a parameter update, which is done after some new measurement is collected, the next step is to incorporate motion into our Gaussian calculations. 
* the measurement update increases our estimation certainty
* the motion update/prediction decreases our certainty
That is because every motion has some chance of under or overshooting its goal, and since motion is not exact, we end up losing some certainty about our exact location after each motion.
4. [1D Kalman Filter](/1D-Kalman-Filter/4.%201D%20Kalman%20Filter.ipynb) 
Last step is to implement a 1D Kalman Filter by putting all these steps together. As a robot moves through the world it locates itself by performing a cycle of:
* sensing and performing a measurement update and
* moving and performing a motion update

### Related Localization Projects 
 [x] [Histogram Filter](https://github.com/tooth2/HistogramFilter)
 [x] [Kalman Filter](https://github.com/tooth2/Kalman-Filter)
 [x] [Particle Filter](https://github.com/tooth2/Robot_Particle_Fillter)
 [x] [2D Extended Kalman Filter](https://github.com/tooth2/Extended-Kalman-Filter)
 [x] [3D Unscented Kalman Filter](https://github.com/tooth2/Unscented-Kalman-Filter)
 [x] [SLAM](https://github.com/tooth2/Landmark-Detection-Tracking-SLAM)

