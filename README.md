# WiROS: WiFi sensing toolbox for robotics

WiROS is a plug-and-play WiFi sensing toolbox allowing researchers to access coarse grained WiFi signal strength (RSSI), fine grained WiFi channel state information (CSI), and other MAC-layer information (device address, packet id’s or frequency-channel information). Additionally, WiROS open-sources state of-art algorithms to calibration and process WiFi measurements to furnish accurate bearing information for received WiFi signals. 

This is an index repository to access the following components of WiROS
1. [**CSI Node**](https://anonymous.4open.science/r/wiros_csi_node-7985/) - Extends the Nexmon CSI toolkit[1] to provide a ROS overlay. 
2. [**Processing Node**](https://anonymous.4open.science/r/wiros_processing_node-ED34/) - Provide calibration and post-processing of WiFi CSI measurments. Open-sources mulitple state-of-art bearing extraction algorithms to measure both the angle of arrival (at the receiver) and angle of departure (from the transmitter) of the WiFi signal.
3. [**RF Messages format**](https://anonymous.4open.science/r/rf_msgs-D2F5/) - Custom ROS messages to structure WiFi measurements information. 

## Overview of Features

1. Easily integrate WiFi channel state measurements, received signal strength and other WiFi MAC-layer information into your robot sensor stack. 
2. Exposes all relevant measurements as accessible ROS topics. See [`rf_msgs`](https://anonymous.4open.science/r/rf_msgs-D2F5/) for more details.  
3. Builds a framework for hassle-free [wireless calibration](https://anonymous.4open.science/r/wiros_processing_node-ED34/README.md#dynamic-compensation) of wireless sensors.
4. Provides visualizations for WiFi signals which are helpful for algorithm paramter tuning and debugging 
5. Open-sources implementation of various state-of-art WiFi processing algorithms[2, 3, 4]. 

## Getting Started

To get started with WiROS, clone these repositories into the `src` folder of your catkin workspace, and follow the [README](https://anonymous.4open.science/r/wiros_csi_node-7985/README.md) in the [CSI Node](https://anonymous.4open.science/r/wiros_csi_node-7985/) to configure your hardware.   

## Example usage of WiROS 

WiROS can be easily leveraged to incorporate WiFi sensors to solve many applicable problems in robotics. We provide the following sample use-cases:

1. **Kidnapped Robot Problem**: A lost robot in an indoor envrionment can be conveniently localized using WiROS. Given a prior map of the existing Access points and additional details of their antenna geometry, the robot's location can be triangulated in a space. 
2. **Correct for Robot Location Drift**: WiFi measurements can be additionally fused with Camera and odometry measurements to more accurately correct for sensor drifts and resolve ambiguities arising from perceptual aliasing in indoor environment[3]. 
3. **IoT device localiztion**: Often IoT devices are hard to localize visually. However, we can leverage WiFi-based bearing measurements to trinagulate their position in the envrionment. This can be useful for both IoT device management or to ensure security/privacy of users in a space. 

### Citations

1. Blanco, Alejandro, et al. "Accurate ubiquitous localization with off-the-shelf ieee 802.11 ac devices." The 19th Annual International Conference on Mobile Systems, Applications, and Services (MobiSys 2021). 2021.
2. Kotaru, Manikanta, et al. "Spotfi: Decimeter level localization using wifi." Proceedings of the 2015 ACM Conference on Special Interest Group on Data Communication. 2015.
3. Arun, Aditya, et al. "ViWiD: Leveraging WiFi for Robust and Resource-Efficient SLAM." arXiv preprint arXiv:2209.08091 (2022).
4. Schmidt, Ralph. "Multiple emitter location and signal parameter estimation." IEEE transactions on antennas and propagation 34.3 (1986): 276-280.
    




