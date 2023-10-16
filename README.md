# HANDS-ON-Jarkom

  Nama  : Choirul RIjal Dawam Iba
  
  NRP   : 5025211206

## TCP Hands On

### NO 1
### Soal
What is the IP address and TCP port number used by the client computer (source) 
that is transferring the alice.txt file to gaia.cs.umass.edu?

### Jawab


Source Address: 192.168.86.68

Source Port: 55639


----------------------------------------------------------------------------------------------------------

### No 2
### Soal
What is the IP address of gaia.cs.umass.edu? On what port number is it sending 
and receiving TCP segments for this connection?

### Jawab

IP Address of gaia.cs.umass.edu: 128.119.245.12

Destination Port: 80

---------------------------------------------------------------------------------------------------------

### No 3
### Soal
* What is the sequence number of the TCP SYN segment that is used to initiate the TCP connection between the client computer and gaia.cs.umass.edu? 
* What is it in this TCP segment that identifies the segment as a SYN segment? 
* Will the TCP receiver in this session be able to use Selective Acknowledgments?

### Jawab

Sequence Number (raw): 4236649187

------------------------------------------------------------------------------------------------------------------------

### No 4
### Soal
*What is the sequence number of the SYNACK segment sent by gaia.cs.umass.edu to the client computer in reply to the SYN? 
*What is it in the segment that identifies the segment as a SYNACK segment?
*What is the value of theAcknowledgement field in the SYNACK segment? 
*How did gaia.cs.umass.edu determine that value?

### Jawab

Sequence Number: 0    (relative sequence number) & Sequence Number (raw): 1068969752, 
Flag 0x012 menandakan segmen SYNACK, 
Acknowledgment number (raw): 4236649188, 
Acknowledgement number didapatkan dari sequence number dari SYN segment ditambah 1 (ACK=Seq no+1).

---------------------------------------------------------------------------------------------------------------------------------------

### no 5
### Soal
*What is the sequence number of the TCP segment containing the header of the HTTP POST command?
*How many bytes of data are contained in the payload (data) field of this TCP segment? 
*Did all of the data in the transferred file alice.txt fit into this single segment?

### Jawab
Sequence Number: 152041  (relative sequence number) & Sequence Number (raw): 4236801228, TCP payload (1385 bytes), No

------------------------------------------------------------------------------------------------------------------------------------

### No 6
### Soal
Consider the TCP segment containing the HTTP “POST” as the first segment in the data transfer part of the TCP connection.

### Jawab

-----------------------------------------------------------------------------------------------------------------------------------------------

### No 7
### Soal
What is the length (header plus payload) of each of the first four data-carrying TCP segments?

### Jawab

---------------------------------------------------------------------------------------------------------------------------------------------------
### No 8
### Soal
*What is the minimum amount of available buffer space advertised to the client by gaia.cs.umass.edu among these first four data-carrying TCP segments?
*Does the lack of receiver buffer space ever throttle the sender for these first four data carrying segments?

### Jawab

---------------------------------------------------------------------------------------------------------------------------------------------------------------

### No 9
### Soal
* Are there any retransmitted segments in the trace file?
* What did you check for (in the trace) in order to answer this question?

### Jawab


------------------------------------------------------------------------------------------------------------------------------------

### No 10
### Soal
* How much data does the receiver typically acknowledge in an ACK among the first ten data-carrying segments sent from the client to gaia.cs.umass.edu?
* Can you identify cases where the receiver is ACKing every other received segment (see Table 3.2 in the text) among these first ten data-carrying segments?

### Jawab


-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

### No 11
### Soal
What is the throughput (bytes transferred per unit time) for the TCP connection?

### Jawab

----------------------------------------------------------------------------------------------------

### No 12
### Soal
Use the Time-Sequence-Graph(Stevens) plotting tool to view the sequence number versus time plot of segments being sent from the client to the gaia.cs.umass.edu server.

### Jawab

---------------------


### No 13
### Soal
These “fleets” of segments appear to have some periodicity. What can you say about the period?

### Jawab

---------------------

## UDP

### No 1
### Soal
* Select the first UDP segment in your trace. What is the packet number of this segment in the trace file?
* What type of application-layer payload or protocol message is being carried in this UDP segment?
* Look at the details of this packet in Wireshark. How many fields there are in the UDP header? Look at the details of this packet in Wireshark. How many fields there are in the UDP header?

### Jawab
Paket 5, SSDP, 4 Field (source port, destination port, length, checksum)

---
### No 2
### Soal
By consulting the displayed information in Wireshark’s packet content field for this packet (or by consulting the textbook), what is the length (in bytes) of each of the UDP header fields?

### Jawab
Masing-masing field adalah 16 bit atau 2 byte, karena ada 4 field maka length masing-masing header dari UDP adalah `8 byte`

---
### No 3
### Soal
The value in the Length field is the length of what?

### Jawab
Length dari paket UDP: payload 275 byte, header 8 byte

---
### No 4
### Soal
What is the maximum number of bytes that can be included in a UDP payload?

### Jawab
Karena length adalah 16 bait field, maximum value nya adalah 65.535, dan headernya 8 byte, maka maximum payload nya adalah 65.527 byte

---

### No 5
### Soal
What is the largest possible source port number?

### Jawab
65.535

---
### No 6
### Soal
What is the protocol number for UDP?

### Jawab

Protocol: UDP (17)

---
### No7
### Soal
Examine the pair of UDP packets in which your host sends the first UDP packet and the second UDP packet is a reply to this first UDP packet.
* What is the packet number of the first of these two UDP segments in the trace file?
* What is the packet number of the second of these two UDP segments in the trace file?
* Describe the relationship between the port numbers in the two packets.

### Jawab
Paket 15, Paket 17, source port dari paket 15 (request) adalah destinasi port untuk paket 17 (reply) dan sebaliknya

----
