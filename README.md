

# Comp midterm net resources :

## Summary

1. [Lookup Table](#lookup-table-)
2. [Quick Delay recap](#quick-delay-recap-)
3. [Abbreviations](#abbreviations-)
4. [Miscellaneous notes](#miscellaneous-notes-)

## Lookup table :
| Subject | Details | File name | Problem | Questions | Details/Note |
|---------|---------|-----------|---------|-----------|--------------|
|HTTP |HTTP Messages and proxy Cache + DNS Resolution | [midterm2018-solved] | 3 | 1.b, 2, 3, 4 | When DNS was resolved, proxy directly SYN to socket without going back to localhost |
|HTTP |HTTP Messages and Proxy Cache, less interesting| [midterm2019-solved] | 2 | 1, 2         | When authoritative DNS server is not the first contacted
|LAB-related|Command|[midterm2019-solved]|2|3|`DIG` command question| 
|HTTP|HTTP Messages, DNS recursive resolution w\ proxy|[midterm2017-solved]|2|1| |
|Attack|Http Persa attack|[midterm2017-solved]|2|3, 4| |
|

## Quick delay recap :

<img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/img/transmission_delay.png?raw=true" alt="transmission_delay" width="50%"/>

<img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/img/propagation_delay.png?raw=true" alt="propagation_delay" width="50%"/>

<img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/img/packet_total_delay_over_switch.png?raw=true" alt="packet_delay" width="50%"/>

<img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/img/good_scheme_HTTP_window.png?raw=true" alt="packet_delay" width="50%"/>

### More notes : 
**Queuing delay** : Approaches infinity if bit arrival rate > bit departure rate i.e. if packets are
processed slower than they arrive, is kinda what we call **burstiness** of the arriving packets 
(arrival rate / departure rate ratio)

## Abbreviations : 

- **RTT** : Round trip time | Time for a *small* packet to go to destination, then for the *small* response to come back.
can be used with most of the packet exchanged in an HTTP SEQ-type exercise because MSS is usually small
- **MSS** : Maximum Segment Size | Usually the size of each segment sent in the HTTP SEQ-type exercises, it is dictated
by network's properties
- **ACK** : Acknowledgement | In response to your request, if it was received, in some exercises can be replaced
with "**200 OK**" (for example in Message SRC-DEST tables to fill)
- **GBN** : Go-Back-N | When a segment is lost, and it has been recognized by the sender, 

## Miscellaneous notes :

- **Pipelining** : Means technique in which multiple requests are written out to a single socket without waiting for the corresponding responses

- **Number of sockets** type of questions : Good rule of thumb is different socket for each 
protocol (UDP, TCP, ETC...) and _also_ different socket for each different server you are communicating with :
ex: epfl.ch vs ethz.ch

- **Slow start** : Is still exponential ^^
- **Fast retransmit** : Can be very important in HTTP SEQ-type exercises. **Without** : Need timeout to retransmit
  (hence usually takes forever), **With** : Needs 3 (Convention, but can change in some exercises) ACKs with wrong
SEQ number to retransmit






[midterm2017-solved]: resources/midterm2017-solved.pdf
[midterm2018-solved]: resources/midterm2018-solved.pdf
[midterm2019-solved]: resources/midterm2019-solved.pdf
