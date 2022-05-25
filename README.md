dreuter.ros2
=========

Installs any version of ros2 via the official ROS repositories (Ubuntu only)

Role Variables
--------------

`ros_distro`: The ROS distribution you want to install, i.e. `foxy`,`galactic`,`humble` or `rolling` (default)
`ros_metapackage`: The ROS metapackage you want to install, i.e. `ros-base` or `desktop` (default)

Example Playbook
----------------

```yaml
- hosts: localhost
  roles:
  - role: dreuter.ros2
    ros_distro: humble
    ros_metapackage: ros-base
```

License
-------

BSD

Author Information
------------------

The best way to contribute to this project is through [github](https://github.com/dreuter/dreuter.ros2). Issues and pull requests are welcome :)
