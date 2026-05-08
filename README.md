# M145 

## IPv4

![alt text](image.png)
![alt text](image-1.png)
![alt text](image-2.png)

## CISCO PAKET Tracer

### Task1
Bitrate in the Terminal
- 9600 Bits per second

WHich command beings with **C**: 
- connect

What commands are displayed with ?
- All possible terminal commands

What commands are displayed with t?
- Telnet Terminal Traceroute

What is enable?
- Enable is a command which makes you enter privileged mode.

type en and press tab
- enable  shows up

Type enable how does the prompt change?
- The prompt changes from > to # which means you are now in privileged mode.

how many commands are displayed in privileged mode?
- There are 12 commands displayed in privileged mode.

Type configure, what message is displayed?
- The message displayed is "Enter configuration commands, one per line. End with CNTL/Z."

Type "show clock" what information is displayed? What is the year that is displayed?
- *6:23:54.675 UTC Mon Mar 1 1993

Type Clock and enter, what is displayed?
- % Incomplete command.

Type clock? What information is displayed?
- set Set the time and date

Type clock set ? What information is asked?
- hh:mm:ss current time

Type clock set 15:00:00 ? What information is asked?
-   <1-31>  Day of the month
  MONTH   Month of the year

Command um die Zeit zu setzten:
clock set 12:00:00 31 January 2035

Type cl *tab* what command is displayed?
- nothing

Type clock, what is displayed?
- incomplete Command

Type "clock set 25:00:00", what information is displayed?
- % Invalid input detected at '^' marker. Bei clock set 25:00:00 wird die Zahl 25 als ungültige Eingabe erkannt, da die Stundenangabe nur von 0 bis 23 reichen darf.

Type clock set 15:00:00 32. What information is displayed?
- % Invalid input detected at '^' marker. Bei clock set 15:00:00 32 wird die Zahl 32 als ungültige Eingabe erkannt, da die Tagesangabe nur von 1 bis 31 reichen darf.

### Task 2

#### Part 1
How many Fast Ethernet interfaces does the switch have?
- 24 Fast Ethernet interfaces

How many Gigabit Ethernet interfaces does the switch have?
- 2 Gigabit Ethernet interfaces

What is the range of values shown for the vty lines?
- 0 to 4

Which command will display the current contents of non-volatile random-access memory (NVRAM)?
- show startup-config

Why does the switch respond with “startup-config is not present?
- Because there is no startup-config file in the NVRAM, which means that the switch has not been configured yet or the configuration has been erased.

---

#### Part 2
What is displayed for the enable secret password?
- The enable secret password is displayed as a hashed value, which is a security measure to protect the actual password from being easily read or accessed.

Why is the enable secret password displayed differently from what we configured?
- The enable secret password is displayed differently because it is stored in a hashed format for security reasons. When you configure the enable secret password, it is encrypted using a one-way hashing algorithm, which means that the original password cannot be easily retrieved or displayed in plain text. This is done to enhance the security of the device and prevent unauthorized access to privileged mode.

If you configure any more passwords on the switch, will they be displayed in the configuration file as plain text or in encrypted form? Explain
- If you configure any more passwords on the switch, they will be displayed in the configuration file in encrypted form. This is because Cisco devices use a hashing algorithm to encrypt passwords for security purposes. When you set a password, it is automatically hashed and stored in the configuration file, making it difficult for unauthorized users to read or access the actual password. This is a standard security practice to protect sensitive information on network devices.

#### Part 3 COnfigure a MOTD Banner
When will this banner be displayed?
- The MOTD (Message of the Day) banner will be displayed when a user attempts to access the switch, either through the console or via remote access (such as Telnet or SSH). It serves as a warning or informational message to users before they log in to the device.
Why should every Swtich have a MOTD banner?
- Every switch should have a MOTD banner to provide important information or warnings to users before they access the device. It can be used to display security warnings, legal disclaimers, or any other relevant information that users should be aware of before logging in. This helps to enhance security and ensure that users are informed about the policies and guidelines for accessing the switch.
- 
#### Part 4: Save and Verify Configuration Files to NVRAM
What is the shortest, abbreviated version of the copy running-config startup-config command?
- Copy run start

Which command will display the contents of NVRAM?
- show startup-config

Are all the changes that were entered recorded in the file?
- Yes, all the changes that were entered in the running configuration are recorded in the startup configuration file when you use the "copy running-config startup-config" command. This ensures that any modifications made to the running configuration are saved and will be applied when the device is rebooted.
How to save the config
- To save the configuration on a Cisco switch, you can use the following command in privileged EXEC mode:

---

### Task 4
CLick the PDU and note the following information:
- Destination MAC Address: 000C:85CC:1DA7
- Source MAC Address: 00D0:D311:C788
- Source IP Address: 172.16.31.5
- Destination IP Address: 172.16.31.2
- At Device: 172.16.31.5

| Device      | Dest. MAC      | Src. MAC       | Src. IPv4   | Dest. IPv4  |
| ----------- | -------------- | -------------- | ----------- | ----------- |
| 172.16.31.5 | 000C:85CC:1DA7 | 00D0:D311:C788 | 172.16.31.5 | 172.16.31.2 |
| Switch 1    | 000C.85CC.1DA7 | 00D0.D311.C788 | 172.16.31.5 | 172.16.31.2 |
| Hub         | 000C.85CC.1DA7 | 00D0.D311.C788 | 172.16.31.5 | 172.16.31.2 |
| 172.16.31.2 | 000C.85CC.1DA7 | 00D0.D311.C788 | 172.16.31.2 | 172.16.31.5 |

---

Repeat the process in Step 1 and gather the information for the following tests:

·         Ping 172.16.31.2 from 172.16.31.3.

·         Ping 172.16.31.4 from 172.16.31.5.

| Device      | Dest. MAC      | Src. MAC       | Src. IPv4   | Dest. IPv4  |
| ----------- | -------------- | -------------- | ----------- | ----------- |
| 172.16.31.3 |                |                | 172.16.31.3 | 172.16.31.2 |
| Hub         | 000C.85CC.1DA7 | 0060.7036.2849 | 172.16.31.3 | 172.16.31.2 |
| 172.16.31.2 | 0060.7036.2849 | 000C.85CC.1DA7 | 172.16.31.2 | 172.16.31.3 |

---

| Device      | Dest. MAC      | Src. MAC       | Src. IPv4   | Dest. IPv4  |
| ----------- | -------------- | -------------- | ----------- | ----------- |
| 172.16.31.5 |                |                | 172.16.31.5 | 172.16.31.4 |
| Switch 1    | 000C.CF0B.BC80 | 00D0.D311.C788 | 172.16.31.5 | 172.16.31.4 |
| 172.16.31.4 | 00D0.D311.C788 | 000C.CF0B.BC80 | 172.16.31.4 | 172.16.31.5 |

---

#### Part 2
Ping 10.10.10.2 from 172.16.31.5

| Device      | Dest. MAC      | Src. MAC       | Src. IPv4   | Dest. IPv4 |
| ----------- | -------------- | -------------- | ----------- | ---------- |
| 172.16.31.5 |                |                | 172.16.31.5 | 10.10.10.2 |
|   xSwitch 1  | 00D0.BA8E.741A | 00D0.D311.C788 | 172.16.31.5 | 10.10.10.2 |
| Router 1    | 0060.2F84.4AB6 | 00D0.588C.2401 | 172.16.31.5 | 10.10.10.2 |
| Swtich 0    | 0060.2F84.4AB6 | 00D0.588C.2401 | 172.16.31.5 | 10.10.10.2 |
| Accesspoint | -----          | --------| --------    | --- |
| 10.10.10.2 | N/A | N/A | 10.10.10.2 | 172.16.31.5 |

#### Reflective QUestions
**Were there different types of cables/media used to connect devices?**
Yes, Copper (Ethernet) and wireless signals.

**Did the cables change the handling of the PDU in any way?** 
No, the PDU remains the same; only the physical encoding changes per medium.

**Did the Hub lose any of the information that it received?**
No, it broadcasted the information to all connected ports.

**What does the Hub do with MAC addresses and IP addresses?**
Nothing. A Hub operates at Layer 1 (Physical) and does not process MAC or IP addresses; it simply repeats the electrical signal.

**Did the wireless Access Point do anything with the information given to it?** 
It converted the frames from a wired format (802.3) to a wireless format (802.11) to bridge the two media.

**Was any MAC or IP address lost during the wireless transfer?**
No, all addressing remained intact for delivery.

**What was the highest OSI layer that the Hub and Access Point used?**
Hub: Layer 1 (Physical). Access Point: Layer 2 (Data Link).

**Did the Hub or Access Point ever replicate a PDU that was rejected with a red “X”?**
No. While the Hub sends the signal everywhere, the receiving device rejects it (the "X") if the MAC doesn't match.

**When examining the PDU Details tab, which MAC address appeared first, the source or the destination?**
The Destination MAC address always appears first in an Ethernet frame.

**Why would the MAC addresses appear in this order?**
To allow switches to read the destination immediately and begin forwarding the frame without waiting for the whole packet (Cut-through switching).

**Was there a pattern to the MAC addressing in the simulation?**
Yes, the first 24 bits (OUI) identified the manufacturer, while the last 24 bits were unique to each virtual interface.

**Did the switches ever replicate a PDU that was rejected with a red “X”?**
No, switches only forward valid frames to the specific destination port found in their MAC table.

**Every time that the PDU was sent between the 10 network and the 172 network, there was a point where the MAC addresses suddenly changed. Where did that occur?**
At the Router. Routers strip the old Layer 2 header and add a new one for the next segment.

**Which device uses MAC addresses that start with 00D0:BA?**
(Refer to your specific Packet Tracer topology; typically the Router's Gigabit interface).

**What devices did the other MAC addresses belong to?**
The NICs (Network Interface Cards) of the PCs and the individual ports of the switches.

**Did the sending and receiving IPv4 addresses change fields in any of the PDUs?**
No, the IP addresses remain constant from source to destination (unless NAT is used).

**When you follow the reply to a ping, sometimes called a pong, do you see the sending and receiving IPv4 addresses switch?**
Yes, the original destination becomes the source for the reply.

**What is the pattern to the IPv4 addressing used in this simulation?**
Hierarchical subnetting: different private IP ranges (10.x.x.x and 172.16.x.x) separated by a gateway.

**Why do different IP networks need to be assigned to different ports of a router?**
To define the boundaries between networks; a router needs distinct interfaces to decide where to route traffic.

**If this simulation was configured with IPv6 instead of IPv4, what would be different?**
Addresses would be 128-bit Hexadecimal, Broadcast would be replaced by Multicast, and the header would be simpler.

### Task 5

Here are the completed answers for the **Examine the ARP Table** task, formatted to match your previous work.

---

## Packet Tracer - Examine the ARP Table

### Part 1: Examine an ARP Request

**Step 1: Generate ARP requests**
* **Is this address (Destination MAC) listed in the table?**
    No. The destination MAC is `FFFF.FFFF.FFFF`, which is a Layer 2 broadcast address. It is not assigned to a specific device in the table.
    
* **How many copies of the PDU did Switch1 make?**
    Three (one for every connected port except the one the PDU arrived on).

* **What is the IP address of the device that accepted the PDU?**
    172.16.31.3

* **What happened to the source and destination MAC addresses (at Layer 2)?**
    They were swapped. The original destination MAC (the specific address of 172.16.31.3) became the Source, and the original Source MAC (172.16.31.2) became the Destination.

* **How many copies of the PDU did the switch make during the ARP reply?**
    Only one. The switch now knows which port leads to 172.16.31.2, so it performs a unicast transmission.

**Step 2: Examine the ARP table**
* **Do the MAC addresses of the source and destination align with their IP addresses?**
    Yes. The source IP 172.16.31.2 matches its MAC, and the destination IP 172.16.31.3 matches its MAC.

* **To what IP address does the MAC address entry correspond (in the ARP table)?**
    172.16.31.3

* **In general, when does an end device issue an ARP request?**
    When it knows the destination IP address but does not know the destination MAC address required to build the Layer 2 Ethernet frame.

---

### Part 2: Examine a Switch MAC Address Table

**Step 1: Generate additional traffic**
* **How many replies were sent and received?**
    4 replies sent, 4 replies received (100% success).

**Step 2: Examine the MAC address table**
* **Do the entries (on Switch 1) correspond to those in the table?**
    Yes. The MAC addresses for the PCs on ports F0/1, F0/2, and F0/3 should match the Addressing Table.

* **Do the entries (on Switch 0) correspond to those in the table?**
    Yes.

* **Why are two MAC addresses associated with one port?**
    Because that port (F0/2) is connected to an Access Point or a Hub that has multiple devices (like 10.10.10.2 and 10.10.10.3) communicating through that single switch interface.

---

### Part 3: Examine the ARP Process in Remote Communications

**Step 1: Generate traffic**
* **What is the IP address of the new ARP table entry?**
    172.16.31.1 (The Gateway/Router interface).

* **How many PDUs appear?**
    Two: one ARP and one ICMP.

* **What is the target destination IP address of the ARP request?**
    172.16.31.1

* **Why (is the destination not 10.10.10.1)?**
    Because the destination IP (10.10.10.1) is on a different subnet. The sender realizes the destination is remote and must send the packet to the Default Gateway (the Router) first. Therefore, it needs the MAC address of the Router, not the final destination.

**Step 2: Examine the ARP table on Router1**
* **How many MAC addresses are in the table? Why?**
    Zero (0). Routers do not typically use a "MAC address table" like switches; they use an ARP cache. Standard routers don't switch frames between ports in the same way a Layer 2 switch does.

* **Is there an entry for 172.16.31.2?**
    Yes, in the ARP table (using `show arp`).

* **What happens to the first ping in a situation where the router responds to the ARP request?**
    The first ping often times out ("Request timed out") because the ARP process takes longer than the ping's initial wait time.

