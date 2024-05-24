# andino_localization

## Overview

The `andino_localization` package provides various odometry algorithms for the Andino robot. Currently, it includes the `rf2o_laser_odometry` algorithm, which is a fast and precise method to estimate the planar motion of a LiDAR from consecutive range scans. This method is useful for mobile robots with inaccurate wheel odometry.

For every scanned point, the `rf2o_laser_odometry` formulates the range flow constraint equation in terms of the sensor velocity and minimizes a robust function of the resulting geometric constraints to obtain the motion estimate. Unlike traditional approaches, this method does not search for correspondences but performs dense scan alignment based on the scan gradients, similar to dense 3D visual odometry.

The very low computational cost (0.9 milliseconds on a single CPU core) combined with its high precision makes `rf2o_laser_odometry` a suitable method for robotic applications that require planar odometry.

For a full description of the `rf2o_laser_odometry` algorithm, please refer to: **[Planar Odometry from a Radial Laser Scanner. A Range Flow-based Approach. ICRA 2016](http://mapir.uma.es/papersrepo/2016/2016_Jaimez_ICRA_RF2O.pdf)** by J. Jaimez and J. Gonzalez.

## Future Work

This package is designed to be easily extendable. New odometry algorithms can be integrated into this package by adding their implementation files to the `src` directory and updating the `CMakeLists.txt` and `package.xml` files accordingly.

## Usage

To run the rf2o_laser_odometry node:

```sh
ros2 launch andino_localization rf2o_laser_odometry.launch.py
```

## Maintainers

hezhexi2002 (hezhexi2002@gmail.com)

## License

This project is licensed under the GPLv3 License - see the LICENSE file for details.

