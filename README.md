# ros2-realtime-example-c

Minimal ROS 2 real-time cookbook recipes, rather than [ros2-realtime-examples](), these examples are written in C which use the [rclc](https://github.com/ros2/rclc) interfaces.


TODO:
- [ ] : add rolling-experimental branch to ros2-realtime-examples-c
- [ ] : add minimal_realtime_loop: shows different  approcahes to created typical real-time time based loops
- [ ] : add minimal_deadline_qos: shows how to use the DDS deadline QoS policy
- [ ] : add minimal_lifecycle: shows how to use node lifecycle to separate configuration and runtime
  real-time phases
- [ ] : add minimal_memory_check: shows how use verify that functions used in the real-time path
  does not allocate dynamic memory
- [ ] : minimal_loan_messages: shows how to use loaned messages APIs
- [ ] : minimal_data_sharing: shows how to use different data sharing approached to avoid
  blocking calls when sharing data between real-time and non real-time threads
- [ ] : minimal_dds_tuning: shows how to use DDS specific configurations to tune real-time
- [ ] : make them run on qnx710

## Requirements

- ROS 2 humble release (now humble only, will add rolling-experimental branch later)
- additional package [rclc](https://github.com/ros2/rclc) humble release (now humble only, will add rolling-experimental branch later)
- Linux based operating system (RT_PREEMPT is not mandatory to run the examples)
- Privileges to set priority, scheduling and memory lock limits. This can be achieved by having
 root privileges or adding user privileges to `/etc/security/limits.conf`


## Build instructions

### Create workspace

```bash
$ mkdir -p ros2_realtime_examples_c_ws/src
$ cd ros2_realtime_examples_c_ws/src
$ git clone https://github.com/Zard-C/ros2-realtime-examples-c.git
# Optional: Build rmw_iceoryx for zero-copy examples
$ git clone https://github.com/ros2/rmw_iceoryx
```

### Install dependencies 

Use [rosdep](http://wiki.ros.org/ROS/Tutorials/rosdep) to install the required dependencies:

```bash
$ cd ros2_realtime_examples_ws
$ rosdep install --from-paths src/ --ignore-src --rosdistro=humble
```

### Build

Build examples

```bash
$ cd ros2_realtime_examples_c_ws
$ colcon build
```

**Note: Some examples might require to install additional RMW implementations**

