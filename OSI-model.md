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

L7 - Application layer

software   ---   protocols
browser          Http/s , FTP
outlook          SMTP
skype            skype-protocol
remote desktop   telnet , RDP


Application layer send data to presentation layer , then presentation layer process that and send it to lower level
L6 - Presentation Layer

- transalation        :   ascii/unicode -> binary
- data compression    :   compression algo like hauffman algo (Text/audio/video) 
- encryption          :   passwords , SSL(secure socket layer)


L5 - Session layer
login to logout

responsible for 
- establishing, managing and terminating connections
- authorization and authentcation


*****  MODERN BROWSER LIKE CHROME TAKE CARES OF TOP 3 LAYERS (7,6,5)   *****



