# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---

## Notes

Videos are located in the 'videos' folder.

PID Project - P - Filename: pid_project_p_only
As shown in the video, using only the proportional parameter of the PID algorithm, we see that the car continues along the track in an oscillating pattern. This behavior is expected as the results of fixing the error causes the steering angle to overshoot and result in further correction of the steering. This event continues on causing larger oscillations until the car leaves the edge of the track.

PID Project - P and D - Filename: pid_project_p_d_only
As shown in the video, the car manages much better on the track after introducing the differential part of the PID algorithm. Even though it completes the track, the beginning displays some slight oscillation effects from the proportional component. This new function improves on itself instead of constantly overshooting the correction to cause further errors.

PID Project - PID - Filename: pid_project_p_d_i
In the final video, combining all three components of the PID algorithm (proportional, differential, and integral) we see a mostly stable car that maintains its position close to the center of the road. Going from the previous video to this one you’ll notice the beginning is better at reducing the oscillation effect and gets to a stable position faster. Further tuning could increase stability on the turns, but I am happy with the results of these parameters.

My final parameters were obtained first by setting the D and I component to 0. Then I started the P component at 1. This resulted in large oscillations occurring with the vehicle. I then reduced the value down to 0.01 and noticed the car would maintain contact on the road for a longer period of time. I then introduced the D component and set that value slightly higher than P. This helped to reduce the oscillations but not by much. It wasn’t until I really brought up the D component value that I noticed better stability in the car. Finally, I introduced the I component and noticed an increase in oscillations when I used a value of 0.01. This meant that it affected the other values too much so I had to reduce it even lower. 0.001 proved to be a good value that positively affected the vehicles position while not negatively affecting the other components.

In the end, the results of implementing each component were what I expected given the labs conducted using Python in the lessons. The P component produced oscillations in the vehicle’s movement. This resulted in an inability to maintain contact with the road after a certain period of time. The D component brought the error down closer to 0 while removing the oscillation pattern from the vehicle’s movement. The I component resulted in the error being brought down faster than without it being added, but the results mostly stayed consistent with having both the P and D component.

## Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets)
  * Run either `./install-mac.sh` or `./install-ubuntu.sh`.
  * If you install from source, checkout to commit `e94b6e1`, i.e.
    ```
    git clone https://github.com/uWebSockets/uWebSockets 
    cd uWebSockets
    git checkout e94b6e1
    ```
    Some function signatures have changed in v0.14.x. See [this PR](https://github.com/udacity/CarND-MPC-Project/pull/3) for more details.
* Simulator. You can download these from the [project intro page](https://github.com/udacity/self-driving-car-sim/releases) in the classroom.

There's an experimental patch for windows in this [PR](https://github.com/udacity/CarND-PID-Control-Project/pull/3)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`. 
