# MoCap Optitrack

This repository contains the ROS node acting has a driver for the NaturalPoint Optitrack motion capture.

#  new-and-old-support-updated

Is the repository branch containing the ROS node version supporting the 1.7+ version of the Motive software. To install this software follow the following steps

```console
git clone https://github.com/TheEngineRoom-UniGe/mocap_optitrack.git
git checkout new-and-old-support-updated
```

The node in this branch has been modified to print in a separate topic the coordinate of each marker, the original version was only publishing the coordinates and orientration of rigid bodies.
The markers coordinates are published in a topic named "/markers" of type "geometry_msgs::PoseArray". At each instant the message contains an array where each array elemetn represent the pose of a single markers.
Markers not belonging to a rigidbody have the "orientation.x" equal to one. While markers belonging to a rigidbody present in the "orientation.x" the ID of their rigidbody.
