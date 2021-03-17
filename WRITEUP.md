# System Integration

> Capstone project of the Udacity Self-Driving Car Engineer course



## Running

Running catkin_make, source devel/setup.sh and roslaunch launch/styx.launch within the ros directory results in no errors and allows the program to connect to the simulator.


Docker hints:

```bash
docker run -p 4567:4567 -v $PWD:/capstone -v /tmp/log:/root/.ros/ --name nd-capstone --rm -it capstone #run container
docker exec -it nd-capstone bash # Connect to running container from other shell, romantic_cannon is a random name given to the container in previous step, probably adding a --name param there would be better.
```

Debugging:
```
rostopic echo /final_waypoints
```


## Rubric

[Detailed Rubric](https://review.udacity.com/#!/rubrics/3058/view).

- [ ] The code is built successfully and connects to the simulator.
- [ ] Waypoints are published to plan Carla’s route around the track.
- [ ] Controller commands are published to operate Carla’s throttle, brake, and steering.
- [ ] Successfully navigate the full track more than once.
