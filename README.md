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

Testing
-------

If you want to test this role locally I setup [`molecule`](https://molecule.readthedocs.io/en/latest/) with [`podman`](https://podman.io/) (a docker alternative). To run the tests you will need to install both.

I would recommend installing `molecule` through `pipx`:
```shell
python3 -m pip install --user pipx
python3 -m pipx ensurepath
pipx install molecule --pip-args molecule-podman
```

We also need to build the containers that are used in the test:
```shell
podman build -t dreuter/ubuntu-ansible-ready:jammy --from ubuntu:jammy ubuntu-ansible-ready
podman build -t dreuter/ubuntu-ansible-ready:focal --from ubuntu:focal ubuntu-ansible-ready
```

Then you can test the playbook with:
```shell
molecule test
```

Author Information
------------------

The best way to contribute to this project is through [github](https://github.com/dreuter/dreuter.ros2). Issues and pull requests are welcome :)
