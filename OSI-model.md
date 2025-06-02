open-systems interconnect 

OSI model is high level diagram of how computer network created/work.

layered systems & protocols(set of rules) that are used for communication between 2 computers

there are 7 layers OSI reference model 

-> Application 
-> Presentation
-> Session 
-> Transport
-> Network
-> Data link
-> Physical 

L7 - APPLICATION LAYER

Software         -   Protocols
browser          -   Http/s , FTP
outlook          -   SMTP
skype            -   skype-protocol
remote desktop   -   telnet , RDP



L6 - PRESENTATION LAYER
Application layer send data to presentation layer , then presentation layer process that and send it to lower level

- transalation        :   ascii/unicode -> binary
- data compression    :   compression algo like hauffman algo (Text/audio/video) 
- encryption          :   passwords , SSL(secure socket layer)


L5 - SESSION LAYER
login to logout

responsible for 
- establishing, managing and terminating connections
- authorization and authentcation


*****  MODERN BROWSER LIKE CHROME TAKE CARES OF TOP 3 LAYERS (7,6,5)   *****

L4 - TRANSPORT LAYER
responsible for transportation of the data 

-segmentation : the data is divided into small segments (seq number + port + data)  that will be transported as a chunk(packet)
example is , we need to send 1000 bytes of data then that 1000 bytes can be divided into 10 segments of 100 bytes 
each segment  have a 
    * sequence number which will be used at the receiving end to identify the main data in the sequence (its not guarantee that seq1 will be received first at receiver side)
    * port number will be used by the software that will lbe listening over that port which will receive the data (eg port 80 is used by browser)

- flow control : this will handle the rate at which the data transportation should happen
example if the server is capable of sending 100Mbps but my host can only process 1Mbps then the host will ask the server to send data with a rate <= 1Mbps

- error control : it is highly probable that data gets lost while transmission through physical layer , for this problem there is automatic repeat request algorithm is used from the receiver side in case any data segment gets lost then the receiver can requst for that particular sequence number data segment
example : segment 1,2 ,3 and 4 send but receiver recieved only 1, 2, and 4 then data segment with sequence number 3 can be requested from the receiver to sender to send again.

in case some data gets lost(or some noise gets added) inside a segment for that case there are checkSum functions to verify data loss/change.

below are the 2 protocols for data transportation 

TCP (transmission control protocol)
1. slow, lossless and feedback
2. connection oriented
3. webPage , email 

UDP (user datagram protocol)
1. fast, lossy , no feedback
2. connection less
3. video chat


L3 : NETWORK LAYER
-> packets ( segments + src + dest IP address)
-> logical addressing (finding IP address of the network from the IP of the destination)
-> routing (mask) using logical addressing to route the call from sender to receiver 
-> path determination (finding the sortest network path as there are multiple path to reach the destination) using graph theory


L2 : DATALINK LAYER
this layer is responsible for sending our datat from our server/Host to the router that will send the data further to destination 
-> there are 3 medium/hardware for connecting from host to router
   - ethernet (NIC card )
   - wifi (wifi chip)
   - fibre optic cable (hardware for fibre optic might be NIC will serve the need for fibre optic as well)

every hardware have a unique MAC address

in Data link layer we have frames which is combination of below 
   MACsource + MACdestination + IPs + IPd + segment + Tail

tail consist of some extra information (Error detection codes, like check sum)  


L1 : PHYSICAL LAYER
We have BITS as the data that is converted into signals, this happens in physical layer

for copper wire : electrical signals __||||___||||  
for fibre optic : laser (ON / OFF) signal are used
fpr wifi : radio signals are used





