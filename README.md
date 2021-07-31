<div align="center">
  <a href="https://react.seas.harvard.edu//">
    <img align="left" src="figs/lab_logo.png" width="180" alt="REACT Lab and WiTech Lab">
  </a>
  <a href="https://react.seas.harvard.edu/communication-sensor">
    <img align="center" src="figs/toolbox_logo.png" width="350" alt="WSR Toolbox">
  </a>
  <a href="https://www.seas.harvard.edu/">
    <img align="right" src="figs/univ_logo.png" width="160" alt="SEAS Harvard and CMU">
  </a>
</div>
<p>&nbsp;</p>

# WiFi-Based  Relative  Bearing  Sensor

WiFi-Sensor-for-Robotics (WSR) toolbox is an open source library, that enables robots in a team to obtain relative bearing to each other by analyzing the phase of their communicated wireless signals as they traverse the environment. Importantly, this capability can be used in non-line-of-sight (NLOS) or visually degraded environements to recover relative spatial positioning information between robots with implications for localization, networking and security amongst others. This toolbox is designed for distributed deployment and real-time operation on robotic platforms using commodity hardware.

![Paper](figs/Paper_logo.png)

The toolbox requires following resources
1. Wireless channel data collected by both signal transmitting and receiving robots.
2. Local displacement of the signal receiving robot. Any pose estimation sensor can be used as long as the input is provided in csv file in the following format:
```
{sec,nsec,x,y,z,yaw,pitch}
``` 
where sec and nsec refer the local timestamp in seconds and nanoseconds respectively; {x,y,z} are the position coordinates.

### Hardware and software requirement with installation steps
1. Wifi Driver and firmware:  [WiFi Driver and Firmware for Wireless channel data (CSI) collection](https://github.com/Harvard-REACT/WSR-Toolbox/wiki/WiFi-Driver-and-Firmware-for-Wireless-channel-data-(CSI)-collection) 
2. Core C++ module : [WSR Toolbox cpp](https://github.com/Harvard-REACT/WSR-Toolbox/wiki/WSR-Toolbox-cpp).

### Code repositories (will be accessible after publication):
1. The core C++ library: [WSR-Toolbox-cpp](https://github.com/Harvard-REACT/WSR-Toolbox-cpp). 
2. Intel 5300 modified wifi driver and firmware : [WSR-WifiDriver](https://github.com/Harvard-REACT/WSR-WifiDriver)
3. Supplementary tool: [WSR-Toolbox-linux-80211n-csitool-supplementary](https://github.com/Harvard-REACT/WSR-Toolbox-linux-80211n-csitool-supplementary)

The wifidriver and supplementary tool repositories are a modified version of code released as part [Linux 802.11n CSI Tool](http://dhalperi.github.io/linux-80211n-csitool/). A detailed explanation of design decision behind the modifications (i.e support for channel reprocity, handling packet collision) can be found in the publication [**Toolbox  Release:  A  WiFi-Based  Relative  Bearing  Sensor  for  Robotics**]()

### Architecture

![Arch](figs/toolbox_architecture.png)


## Open-Source Datasets
These dataset are collected for indoor environments in LOS and NLOS for different robot trajectories
1. [WSR-Toolbox-Dataset](https://github.com/Harvard-REACT/WSR-Toolbox-Dataset)


## Performance Evaluation

### AOA profile obtained using 3D robot motion
<div align="center">
  <img align="left" src="figs/drone_3D_motion.gif" width="250" alt="drone Trajectory">
  <img align="center" src="figs/sample_3D_traj.png" width="250" alt="traj plot">
  <img align="right" src="figs/sample_profile.png" width="220" alt="aoa profile">
</div>
<p>&nbsp;</p>

The bearing angle i.e Angle-of-Arrival accuracy for a dataset in NLOS using groundtruth and T265 Tracking camera trajectory:
![NLOS_Set_B_AOA](figs/NLOS_Set_B_2D_Trajectory_AOA_Accuracy_Results.png)


### Use case: Localization
![Testbed map](figs/Localization_dataset_2D_traj.png)

The transmitting robot positions are assumed to be know. The receiving robot can localize itself using the bearing angle calculated from our framework. We use the profile variance metric discussed in [**Toolbox  Release:  A  WiFi-Based  Relative  Bearing  Sensor  for  Robotics**]() to reject outlying measurements. The localization accuracy for non-line-of-sight using all onboard sensing obtained for one of our datasets:

<div align="center">
  <img align="center" src="figs/NLOS_accuracy_using_thresholding_gt_traj.png" width="400" alt="Localization NLOS accuracy gt">
  <img align="center" src="figs/NLOS_accuracy_using_thresholding.png" width="400" alt="Localization NLOS accuracy">
</div>
<p>&nbsp;</p>


## Citation
- [1] Jadhav Ninad*, Weiying Wang*, Diana Zhang, O. Khatib, Swarun Kumar and Stephanie Gil. [**WSR: A WiFi Sensor for Collaborative Robotics**](https://arxiv.org/abs/2012.04174)

```bibtex
@article{Jadhav2020WSRAW,
  title={WSR: A WiFi Sensor for Collaborative Robotics},
  author={Ninad Jadhav and Weiying Wang and Diana Zhang and O. Khatib and Swarun Kumar and Stephanie Gil},
  journal={ArXiv},
  year={2020},
  volume={abs/2012.04174}
}
```

- [2] Jadhav Ninad, Weiying Wang, Diana Zhang, Swarun Kumar and Stephanie Gil. [**Toolbox  Release:  A  WiFi-Based  Relative  Bearing  Sensor  for  Robotics**]().
 

## Acknowledgments
We  gratefully  acknowledge  funding  support  through  the NSF and MIT Lincoln Laboratories. Experiments were conducted in the the REACT Lab.

## License

[BSD License](LICENSE.BSD)