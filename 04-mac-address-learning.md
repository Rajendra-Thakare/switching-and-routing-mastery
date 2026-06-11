# Topic 3 & 4: Process of an Ethernet Switch & MAC Learning

## The Processing Pipeline
When an Ethernet frame hits a switch port, the internal hardware executes these steps:
1. **FCS Check:** The switch verifies the Frame Check Sequence trailing code. If corrupted, the frame is instantly dropped.
2. **Source MAC Learning:** The switch inspects the frame's Source MAC and updates its CAM table.
3. **Destination Lookup:** The switch searches its CAM table for the Destination MAC.
4. **Forwarding Decision:** If known, it forwards out that single egress port. If unknown or a broadcast, it floods it out all active ports except the ingress port.

## How a Switch Learns MAC Addresses
* Switches maintain a dynamic table in memory called the **CAM (Content Addressable Memory) Table** or **MAC Address Table**.
* The table maps a specific **MAC Address** to a physical **Switch Port Number**.
* **The Aging Timer:** To keep the table clean, entries don't stay forever. In default configurations (like Cisco switches), an inactive MAC address entry expires and is deleted after **300 seconds (5 minutes)** if no new traffic is received from that device.

