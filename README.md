# AFIT Swarm Simulation
This repository contains the code for modeling UAV swarms using Hardware-in-the-Loop (HIL) to connect [Pixhawk](https://pixhawk.org/choice)<sup>[\[1\]](#myfootnote1)</sup> autopilots to instances of [JSBSim](http://jsbsim.sourceforge.net/).

A Sept 2015 version of the OpenEaagles simulation framework ('OpenEaagles' and 'OpenEaagles3rdParty' directories) is included as well as extension to that framework ('OpenEaaglesSwarmSims') that enables the modeling of UAV swarms.

For the latest OpenEaagles source code, see: [GitHub](https://github.com/doughodson) or [OE](http://www.openeaagles.org/)

The Excel spreadsheet title "UAV_Waypoints.xlsx" generates random swarming UAVs used in the swarmSim project.

### SIMDIS description
_SIMDIS_ with a _DIS_ plugin is used to provide the visual interface for simulations in this project.

SIMDIS™ is a set of software tools that provide two and three-dimensional interactive graphical and video display of live and post processed simulation, test, and operational data. SIMDIS has evolved from a Naval Research Laboratory display tool for the output of missile models to a premier government off the shelf (GOTS) product for advanced situational awareness and visual analysis. Since its inception, the toolkit has experienced significant user base growth with over 16,000 current registrations.

SIMDIS is targeted for Linux and Windows that have hardware accelerated 3D graphics.

### SIMDIS Installation:
Download and install [SIMDIS](https://simdis.nrl.navy.mil)
- You will need to create an account to access the site
- From the **Menu** under "_Downloads\Archives\SIMDIS 9.5.0 (SR7)_" select `Download Full`
- Select and download the appropriate installer for your system
- Follow installer directions

Download and install DIS plugin
- Download and follow directions in **SIMDIS_DIS_Plugin.pdf**  
  (From the **Menu** under "_Downloads\Archives\Plug-ins\DIS\DIS Plug-in Documentation_")

### SwarmSim Installation and Setup
1. Install **Visual Studio 2013**
2. Install **SIMDIS**
3. Clone or unzip this repository to your computer
4. Double-click on _afit-swarm-simulation\OpenEaagles\build\premake\_**make.bat**
5. Open _afit-swarm-simulation\OpenEaagles\build\vs2013\_**oe.sln** with VS2013 and built project
  - Right click "Solution 'oe' (15 projects)"
  - Select "Build Solution" `(F7)`
  - Verified "_Build: 15 succeeded, 0 failed, 0 up-to-date, 0 skipped_"
  - Close VS2013
6. Open _afit-swarm-simulation\OpenEaaglesSwarmSims\build\vs2013\_**swarmdev.sln** with VS2013 and built project
  - Right click "Solution 'swarmdev' (2 project)"
  - Select "Build Solution" `(F7)`
  - Verified "_Build: 2 succeeded, 0 failed, 0 up-to-date, 0 skipped_"
7. You are now ready to simulate UAV swarms using HIL
  - Edit _swarm.epp_ to configure your swarm<sup>[\[2\]](#myfootnote2)</sup>
  - Run the batch file, _makeEdl.bat_, to compile your inputs into an EDL file, _swarm.edl_
  - Right-click **swarmSim** and select "_Set as StartUp Project_" if not already set
  - Press `(F5)` or click the `Local Windows Debugger` play button to run the project
8. View your swarm using SIMDIS
  - Startup SIMDIS and load the DIS plugin if not automatically loaded
  - From the "_Plug-in Tools_" menu, select "_DIS..._" or press `([)`
  - Under _Network Settings_, ensure "_DIS IP Address_" and "_Network Interface_" are  
    both set to **127.0.0.1** and "_DIS Port_" is set to **3000**
  - Click the `Connect` button and `Close`
  - You should now see your swarm and have the ability to interact with it (i.e. pan, tilt, zoom, follow, etc.)

<sub><a name="myfootnote1">[1]</a> Note: Pixhawk autopilots used here are flashed with the px4fmu-v2\_default.px4 firmware Standard Version (stable) using [QGroundControl](https://pixhawk.org/firmware/downloads). To increase fight stability while swarming, the FW\_P\_LIM\_MAX parameter (positive pitch limit) was changed from its default value of 45.0 to 15.0. FW\_P\_RMAX\_POS and FW\_P\_RMAX\_NEG (maximum positive and negative pitch rates) were both changed from their default value of 60.0 to 10.0. All other parameters remained unchanged from their default values. Also note that the Pixhawk safety switch must be installed and used to disable the safety mode.</sub>

<sub><a name="myfootnote2">[2]</a> For more information on the Eaagles Definition Language (i.e. understanding how to configure .epp and .edl files), see _Basic Package Classes Slides_ under the [Documentation](http://www.openeaagles.org/wiki/doku.php?id=documentation:documentation) section of the OpenEaagles website.</sub>
