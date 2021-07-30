<div align="center">
  <a href="https://react.seas.harvard.edu//">
    <img align="left" src="figs/REACT_logo.jpg" width="120" alt="REACT Lab">
  </a>
  <a href="https://react.seas.harvard.edu/communication-sensor">
    <img align="center" src="figs/toolbox_logo.png" width="300" alt="WSR Toolbox">
  </a>
  <a href="https://www.seas.harvard.edu/">
    <img align="right" src="figs/SEASLogo_RGB.jpg" width="150" alt="SEAS Harvard">
  </a>
</div>
<p>&nbsp;</p>

# WiFi-Based  Relative  Bearing  Sensor

WiFi-Sensor-for-Robotics (WSR) toolbox is an open source library, that enables robots in a team to obtain relative bearing to each other by analyzing the phase of their communicated wireless signals as they traverse the environment. Importantly, this capability can be used in non-line-of-sight (NLOS) or visually degraded environements to recover relative spatial positioning information between robots with implications for localization, networking and security amongst others. This toolbox is designed for distributed deployment and real-time operation on robotic platforms using commodity hardware.

The following inputs are required:
1. Wireless channel data collected by both signal transmitting and receiving robots. Refer the wiki [WiFi Driver and Firmware for Wireless channel data (CSI) collection](https://github.com/Harvard-REACT/WSR-Toolbox/wiki/WiFi-Driver-and-Firmware-for-Wireless-channel-data-(CSI)-collection) for details about software and hardware requirements and installation steps.
2. Local displacement of the signal receiving robot. Any pose estimation sensor can be used as long as the input is provided in csv file in the following format:
```
{sec,nsec,x,y,z,yaw,pitch}
``` 
where sec and nsec refer the local timestamp in seconds and nanoseconds respectively; {x,y,z} are the position coordinates.

The core C++ library can be accessed [here](https://github.com/Harvard-REACT/WSR-Toolbox-cpp). The installation intructions can be found in the Wiki page [WSR Toolbox cpp](https://github.com/Harvard-REACT/WSR-Toolbox/wiki/WSR-Toolbox-cpp).

### Architecture
The overall architecture is as follows:

![Testbed map](figs/toolbox_architecture.png)



## Open-Source Datasets

https://github.com/Harvard-REACT/WSR-Toolbox-Dataset



## Citation

## Acknowledgments


## License

[BSD License](LICENSE.BSD)