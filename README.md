# Capstone: System Integration

> Capstone Project of the Udacity Self-Driving Car Nanodegree: Programming a Real Self-Driving Car.

**This repo is bsed on the Docker setup.**

## Docker Installation

[Install Docker](https://docs.docker.com/engine/installation/)

1. Clone this project repository
```bash
git clone git@github.com:joustava/CarND-Capstone.git
```

2. Build the Docker image from the Dockerfile available in the repository
```bash
docker build . -t capstone
```

3. Start a container based on the previously build image
```bash
docker run -p 4567:4567 -v $PWD:/capstone -v /tmp/log:/root/.ros/ --rm -it capstone
```

## Running the project

Within the running container

1. Change to the catkin workspace
```bash
cd ros
```

2. Build the workspace
```bash
catkin_make
```

3. Source the scripts
```bash
source devel/setup.sh
```

4. Run the project
```
roslaunch launch/styx.launch
```

To see the result you need to first download the [simulator](https://github.com/udacity/CarND-Capstone/releases) for your system and unzip the package.
You probably need to change the permissions e.g: `chmod -R u+x ~/Downloads/mac_sys_int` (path to wherever you unzipped the files). Then you can click the 
`sys_int` application, it should connect to the ROS application and the car will start acting upon the data it receives.

## Real world testing
1. Download [training bag](https://s3-us-west-1.amazonaws.com/udacity-selfdrivingcar/traffic_light_bag_file.zip) that was recorded on the Udacity self-driving car.
2. Unzip the file
```bash
unzip traffic_light_bag_file.zip
```
3. Play the bag file
```bash
rosbag play -l traffic_light_bag_file/traffic_light_training.bag
```
4. Launch your project in site mode
```bash
cd CarND-Capstone/ros
roslaunch launch/site.launch
```
5. Confirm that traffic light detection works on real life images

### Other library/driver information
Outside of `requirements.txt`, here is information on other driver/library versions used in the simulator and Carla:

Specific to these libraries, the simulator grader and Carla use the following:

|        | Simulator | Carla  |
| :-----------: |:-------------:| :-----:|
| Nvidia driver | 384.130 | 384.130 |
| CUDA | 8.0.61 | 8.0.61 |
| cuDNN | 6.0.21 | 6.0.21 |
| TensorRT | N/A | N/A |
| OpenCV | 3.2.0-dev | 2.4.8 |
| OpenMP | N/A | N/A |

We are working on a fix to line up the OpenCV versions between the two.
