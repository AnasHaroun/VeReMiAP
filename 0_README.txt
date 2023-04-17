'''
Created on May 21, 2020
@author: Mohammed Abdelmaguid (18ma5@queensu.ca)
'''

Documentation

This file describes Version 1.0 of the "VeReMi_Pro" dataset, the data collection process and the logged measurements.

The information included in this documentation is as follows:

- Dataset Description
- Data Collection Software
- Scenario Description
- Attack Model Description
- Data Size and Format
- Logged Data
- File Structure
- Dataset Download
- License


Dataset Decription

The collection and construction of this synthetic network dataset is an extended version of the VeReMi dataset, built using the Framework For Misbehavior Detection (F2MD). The new dataset incorporates three key elements - CAM messages, a newly added class of attacks known as the ``Fake Reporting Attack," and an evaluation of the impact of this attack, which in this case manifests as a road hazard.

Data Collection Software

The SUMO tool is utilized to create realistic network mobility traffic. The generated traffic is then imported into OMNeT++ in the second element, where the network traffic is generated utilizing both Veins and INET. The INET framework, as an open-source model library, is specifically designed for communication networks. The Traffic Control Interface (TraCI) was used for real-time access and manipulation of road traffic simulations.

Scenario Description

The Luxembourg SUMO Traffic (LuST) Scenario was selected as the network for this study. LuST is a highly realistic VANET simulation that incorporates real-world data, including a diverse range of vehicles and traffic conditions, such as intersections, roundabouts, and highways.

Attack model Description

In our simulation of VANET, both malicious and benign vehicles were included to emulate potential cyber attacks. The malicious vehicles were designed to execute a range of malicious actions by transmitting false messages about themselves or the road conditions. To complement these malicious vehicles, the simulation also consisted of legitimate vehicles that followed predetermined routes and engaged in communication with each other, replicating the behavior of vehicles in a typical VANET environment. We introduced a novel fake reporting attack, which is a CAM-related attack. This attack occurs when a malicious vehicle sends false information about the road conditions, leading other vehicles to take evasive actions. Our chosen scenario involved reporting a fake accident, which can cause confusion and potentially lead to a real accident.

Data Size and Format

The synthetic network dataset employed in this study was comprised of 2 gigabytes of data, represented in the form of JSON files. These files captured the exchange of messages between individual vehicles and other vehicles in the network. The messages were organized chronologically, and each file contained both BSMs and CAMs. The interval between each message was set to one second. In our dataset, each record corresponds to either a BSM or a CAM and encompasses the standard data fields present in each of these messages. In addition to the standard BSM's data fields, the dataset included two additional fields crucial to the study's objective. The first field, referred to as the ``Fake accident attack" indicates an attack message that transmits false information. The second field, the ``Attack effect," reflects the time at which the corresponding hazard event occurs. It is worth noting that the attack effect field is not directly associated with the attack message in terms of timing, as the messages themselves serve as timestamps to identify the occurrence of the hazard.

Logged Data

The logged measurements include a wide range of data points that are relevant to the analysis of messages and attacks in the VANET. This data includes, but is not limited to, the message ID, as well as the send and receive times for each message, along with the associated vehicle ID. In addition, we collected information about the position and speed of the vehicle in the x, y, and z axes, as well as the GPS coordinates of the message sender. To provide additional context for the analysis, we also collected data on environmental factors such as road number, lane position, and maximum speed limit on the road. Finally, we included information related to the attacks, including the type of attack and its effect on the VANET. Together, these measurements provide a comprehensive view of the messages and attacks on the network.

The following list provides the names of the logged parameters:

•	Message ID
•	Send Time
•	Receive Time
•	Vehicle ID
•	Position 
•	Speed
•	Acceleration
•	Sender GPS
•	Event ID                                                                     
•	Road number
•	Lane Index
•	Lane Position
•	Max speed limit on the road
•	Max Deceleration
•	Current Direction
•	Type of attack (fake reporting attack, among others)
•	Effect of the attack (hazard)


File Structure:

This is the shape of the file structure in the current version of the dataset

VeReMiPro/
├── 1/
    ├── traceJSON-9-7-A0-1-0.json
    ├── traceJSON-15-13-A0-1-0.json
    ├── .....
├── 2/
    ├── traceJSON-9-7-A0-1-0.json
    ├── traceJSON-15-13-A0-1-0.json
    ├── traceJSON-27-25-A0-3-0.json
    ├── ......
├── ......	
├── LICENSE.txt
├── README.txt


Dataset Download

To download the dataset from Scholars Portal Dataverse, it is recommended to select all files and download them at once in their original format. This ensures that the file structure described in the previous section is preserved.
















