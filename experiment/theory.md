#### Introduction
Circuit Switching is a communication method where a dedicated communication path (circuit) is created between the sender and receiver before any data is sent. This circuit stays active for the entire duration of the communication and is released only after the communication ends.  
The telephone system network is one of the examples of Circuit switching. FDM (Frequency Division Multiplexing) and TDM (Time Division Multiplexing) are two methods of multiplexing multiple signals into a single carrier.

**Frequency Division Multiplexing (FDM):** It is used when multiple data signals are combined for simultaneous transmission via a shared communication medium. It is a technique by which the total bandwidth is divided into a series of non-overlapping frequency sub-bands, where each sub-band carries different signal. Practical use in radio spectrum & optical fiber to share multiple independent signals.  
**Time Division Multiplexing (TDM):** It is a method of transmitting and receiving independent signals over a common signal path using synchronized switches at each end of the transmission line. TDM is used for long-distance communication links and bears heavy data traffic loads from the end user. TDM is also known as a digital circuit switch.

<center>
    <img style="mix-blend-mode: darken;" src="images\circuit switching.png" alt="Circuit Switching" width="500";height="400">
    <figcaption style="font-weight: bold;"> Fig. 1 Visual Representation of Circuit Switching</figcaption>
</center>

#### Phases of Circuit Switching
- **Circuit Establishment:** A dedicated circuit between the source and destination is constructed via a number of intermediary switching centers. Communication signals can be requested and received when the sender and receiver communicate signals over the circuit.

- **Data Transfer:** Data can be transferred between the source and destination once the circuit has been established. The link between the two parties remains as long as they communicate.

- **Circuit Disconnection:** Disconnection in the circuit occurs when one of the users initiates the disconnect. When the disconnection occurs, all intermediary linkages between the sender and receiver are terminated.

#### Switch
In computer networking, a switch is a device that connects multiple devices together within a local area network (LAN) and allows them to communicate with each other by forwarding data packets.  

<center>
    <img style="mix-blend-mode: darken;" src="images\switch.png" alt="Switch" width="500" > <figcaption style="font-weight: bold;"> Fig. 2 Switch Device </figcaption>
</center>


#### Working of Switch
1. **Receiving data:** When a device sends data, it's encapsulated in a frame with a destination MAC address.  
2. **Examining the address:** The switch receives the frame and examines the destination MAC address.  
3. **Looking up the address:** The switch consults its internal MAC address table to find the corresponding port for the destination device.  
4. **Forwarding the data:** If the destination is found, the switch forwards the frame only to that specific port.  
5. **Building the table:** Initially, the switch may not know all MAC addresses. It learns them by observing traffic and adding them to its table.  
6. **Handling unknown destinations:** If the destination MAC address is not in the table, the switch will forward the frame to all ports (broadcast) to try and locate it, but will then update its table.

**Example of Switch Operation:**
- Device A (MAC Address 00-14-22-01-23-45) sends a frame to Device B.  
- The switch receives the frame on Port 1 and logs “00-14-22-01-23-45” to the MAC Address Table under Port 1.  
- When Device B responds, its MAC address is similarly logged under Port 2.  
- Future communication between Device A and Device B occurs directly between Ports 1 and 2 without unnecessary broadcasting.  


#### MAC Address
MAC stands for Media Access Control. It is a physical address that uniquely identifies a device and hardware manufacturer on a network.  

<center>
<img style="mix-blend-mode: darken;" src="images\mac.jpg" alt="MAC Address"  width="400">
<figcaption style="font-weight: bold;">Fig. 3 Representation of MAC</figcaption>
</center> 

A MAC Address is a 12-digit hexadecimal number (48-bit binary number), which is mostly represented by Colon-Hexadecimal notation. MAC address can be represented using any of the following formats:  

<center>
<img style="mix-blend-mode: darken;" src="images\mac-notation.jpg" alt="MAC Address"  width="400">
<figcaption style="font-weight: bold;">Fig. 4 Format of MAC Address</figcaption>
</center>

#### MAC Address Table
A MAC address table, also known as a CAM (Content Addressable Memory) table, is where the switch stores information about the other Ethernet interfaces to which it is connected on a network. The table enables the switch to send outgoing data (Ethernet frames) on the specific port required to reach its destination, instead of broadcasting the data on all ports (flooding).  

The MAC address table can contain two types of entries:
- **Static:** Static entries are manually added to the table by a switch administrator. Static entries have higher priority than dynamic entries. Static entries remain active until they are removed by the switch administrator.  
- **Dynamic:** Dynamic entries are automatically added to the table through a process called MAC learning, in which the switch retrieves the source MAC address (and VLAN ID, if present) of each Ethernet frame received on a port. If the retrieved address does not exist in the table, it is added. Dynamic entries remain in the table for a predetermined amount of time (defined with the command mac-address-table age-time), after which they are automatically deleted.  

 <center>
<img style="mix-blend-mode: darken;" src="images\cam-table.png" alt="MAC Address Table"  width="500">
<figcaption style="font-weight: bold;">Fig. 5 MAC/CAM Address Table</figcaption>
</center>

#### How a MAC Address Table Works
- **Learning:** Learns MAC addresses by checking the source MAC of incoming frames.  
- **Forwarding:** Uses the MAC table to send frames to the correct port.  
- **Aging:** If a MAC address isn't seen for a while, it's removed from the table (to keep it updated).  


#### Difference between Circuit Switching and Packet Switching

| S.No. | Circuit Switching | Packet Switching |
|-------|------------------|------------------|
| 1 | Circuit Switching is a method of communication where a dedicated path (or circuit) is created between two devices before they start exchanging data. This path remains active and reserved only for them until their communication is over. | Packet switching is a communication method where data is divided into smaller units called packets and transmitted over the network. Each packet contains the source and destination addresses, as well as other information needed for routing. |
| 2 | Circuit switching is more reliable. | Packet switching is less reliable. |
| 3 | Wastage of resources is more in Circuit Switching. | Less wastage of resources as compared to Circuit Switching. |
| 4 | In Circuit Switching, there is a physical path between the source and the destination. | In Packet Switching, there is no physical path between the source and the destination. |
| 5 | e.g., landline calls | e.g., E-mail send |

<center> 

**Table: Difference between Circuit Switching and Packet Switching** 
</center>


#### Applications of Circuit Switching
- Telephone networks: For real-time voice calls with dedicated lines.  
- Integrated Services Digital Network (ISDN): For voice and data transmission over digital lines.  
- Leased lines: Used by businesses for secure, fixed communication.  
- Emergency systems: Ensures uninterrupted communication during crises.  
- Old LANs: Used in earlier local networks for direct device connections.  


#### Advantages of Circuit Switching
- Good for voice and video calls.  
- No delay once the path is made.  
- Data arrives in the correct order.  


#### Disadvantages of Circuit Switching
- Wastes resources if no data is being sent.  
- Takes time to set up the connection.  
- Not ideal for internet or short data messages.  
