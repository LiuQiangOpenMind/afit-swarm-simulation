# AFIT Swarm Simulation

This repository contains the code for modeling UAV swarms using Hardware-in-the-Loop to connect [Pixhawk](https://pixhawk.org/choice) autopilots to instances of [JSBSim](http://jsbsim.sourceforge.net/).

A Sept 2015 version of the OpenEaagles simulation framework ('OpenEaagles' and 'OpenEaagles3rdParty' directories) is included as well as extension to that framework ('OpenEaaglesSwarmSims') that enables the modeling of UAV swarms.

For the latest OpenEaagles source code, see: [GitHub](https://github.com/doughodson) or [OE](http://www.openeaagles.org/)

The Excel spreadsheet title "UAV_Waypoints.xlsx" generates random swarming UAVs used in the swarmSim project.

### SIMDIS

SIMDIS with a DIS plugin is used to provide the visual interface for simulations
in this project.

SIMDIS™ is a set of software tools that provide two and three-dimensional
interactive graphical and video display of live and post processed simulation,
test, and operational data. SIMDIS has evolved from a Naval Research Laboratory
display tool for the output of missile models to a premier government off the
shelf (GOTS) product for advanced situational awareness and visual analysis.
Since its inception, the toolkit has experienced significant user base growth
with over 16,000 current registrations.

SIMDIS is targeted for Linux and Windows that have hardware accelerated 3D graphics.
A copy of SIMDIS can be found at [simdis](https://simdis.nrl.navy.mil/).
