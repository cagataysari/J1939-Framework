[![Travis Build Status](https://travis-ci.org/famez/J1939-Framework.svg?branch=master)](https://travis-ci.com/famez/J1939-Framework)

# J1939-Framework
Framework to work with J1939 protocol. 

J1939 protocol is a standard used in different systems compliant with CAN 2.0B specification.

The framework has been developed in C++ in a Linux distribution and compiled using the GNU toolchain. No dependencies are required for the compilation of any of the projects except from SocketCan compiled in the Linux Kernel.



## What can you do with J1939-Framework

- Save can frames from the Can Bus into recordings in TRC format with BinUtils/TRCDumper.
- Play can frames from recordings in TRC format into the Can Bus with BinUtils/TRCPlayer.
- Convert TRC files into pcap files readable by wireshark with BinUtils/TRCToCap.
- Dissect pcap files with wireshark and the J1939 plugin dissector (wireshark/dissector).
- Sniff frames from the Can Bus compliant with J1939 protocol with BinUtils/j1939Sniffer.
- Decode raw J1939 data to human readable data with BinUtils/j1939Decoder.
- Craft your own J1939 frames and send them to the Can Bus with BinUtils/j1939Sender. The functionality can be extended with the help of bash scripts located in Scripts (some examples are listed).
- Visualize what is going on in the Can Bus with GUI_WEB. You will be able to craft, send and visualize the frames that are flowing in the Bus as well as visualizing graphics of their content (SPNs).
- Discover J1939 devices with BinUtils/j1939AddressMapper.
- Simulation of the Address Claim Process with BinUtils/j1939AddrClaim.

### And of course, develop!!:

- In CAN/ folder we can find a library in C++ (libCAN.so) with methods to generate and sniff can frames with support for PeakCan and SocketCan.
- In J1939/ folder we can find a library in C++ (libJ1939.so) to easily manipulate J1939 frames and work with the J1939 protocol. Some features are:
	Support of BAM protocol.
	A factory class in charge of generating the J1939 frames.
	A database loaded by the factory located in Database/frames.json with a list of the most used Application Layer frames (including the FMS protocol).
	Coding/Decoding DM1 (Diagnosis), FMS1 (TTS), Request and Address Claim frames.
	Coding/Decoding of SPNs (String, status and numeric).


## Installing and compiling

# Requirements:
General:
- Linux distribution with SocketCan support.
- Cmake 3.5.1 or higher.
- JsonCpp

j1939Gui (if the dependencies are not satified, this application is not compiled):
- libwebsockets
- protobuf >= 3.0.0

j1939Decoder (if the dependencies are not satified, this application is not compiled):
- ncurses

TRCToCap (if the dependencies are not satified, this application is not compiled):
- glib2.0

Steps:

Steps can be found in travis.yml file.
    
## TRCPlayer

![alt text](https://github.com/famez/J1939-Framework/blob/master/BinUtils/TRCPlayer/TRCPlayer.png)

    
## Wireshark dissector

![alt text](https://github.com/famez/J1939-Framework/blob/master/wireshark/dissector/J1939-plugin.png)

## J1939GUI

![alt text](https://github.com/famez/J1939-Framework/blob/master/Graph.png)

![alt text](https://github.com/famez/J1939-Framework/blob/master/GUI_WEB/J1939GUI.png)
