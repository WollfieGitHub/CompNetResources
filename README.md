

# Comp midterm net resources :

## Summary

1. [Lookup Table](#lookup-table-)
2. [Abbreviations](#abbreviations-)
3. [Quick Delay recap](#quick-delay-recap-)
4. [Miscellaneous notes](#miscellaneous-notes-)

## Lookup table :
| Subject | Details | File name | Problem | Questions | Details/Note |
|---------|---------|-----------|---------|-----------|--------------|
|HTTP |HTTP Messages and proxy Cache + DNS Resolution | [midterm2018-solved] | 3 | 1.b, 2, 3, 4 | When DNS was resolved, proxy directly SYN to socket without going back to localhost |
|HTTP |HTTP Messages and Proxy Cache, less interesting| [midterm2019-solved] | 2 | 1, 2         | When authoritative DNS server is not the first contacted
|LAB-related|Command|[midterm2019-solved]|2|3|`DIG` command question| 
|HTTP|HTTP Messages, DNS recursive resolution w\ proxy|[midterm2017-solved]|2|1| Recursive is d1 <=> d2 <=> d3, iterative is the other one|
|Attack|Http Persa attack|[midterm2017-solved]|2|3, 4| |
|HTTP |GBN vs Sel. Rep.  |[midterm2017-solved]|3|1, 2

## Abbreviations :

- **RTT** : Round trip time | Time for a *small* packet to go to destination, then for the *small* response to come back.
  can be used with most of the packet exchanged in an HTTP SEQ-type exercise because MSS is usually small
- **MSS** : Maximum Segment Size | Usually the size of each segment sent in the HTTP SEQ-type exercises, it is dictated
  by network's properties
- **ACK** : Acknowledgement | In response to your request, if it was received, in some exercises can be replaced
  with "**200 OK**" (for example in Message SRC-DEST tables to fill)
- **GBN** : Go-Back-N | The receiver has a window of **size 1**, it's willing to accept only one SEQ at a time and discards
  anything else. Sender retransmits all sent after last ACKed segment, because it knows receiver has discarded them all.
ACKs are **Cumulative** means if there is **ACK 143**, all BITS from 0 to 143 were correctly acknowledged
- **SR** : Selective repeat | Receiver has window size of K, ACKs are **Selective** means that if ACK 10, 
segment 10 has been ACKed. If lost, only the lost segment is retransmitted

## Quick delay recap :

<img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/img/transmission_delay.png?raw=true" alt="transmission_delay" width="50%"/>

<img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/img/propagation_delay.png?raw=true" alt="propagation_delay" width="50%"/>

When there is a packet switch in the middle of two links:

<img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/img/packet_total_delay_over_switch.png?raw=true" alt="packet_delay" width="50%"/>


### More notes : 
**Queuing delay** : Approaches infinity if bit arrival rate > bit departure rate i.e. if packets are
processed slower than they arrive, is kinda what we call **burstiness** of the arriving packets
(arrival rate / departure rate ratio)

## Miscellaneous notes :

- **Pipelining** : Means technique in which multiple requests are written out to a single socket without waiting for
  the corresponding responses. Implies introduction of sliding window of size N.
  **Contrary of STOP and WAIT** which is send ONE segment and wait for ACK before sending TWO

- **Number of sockets** type of questions : Good rule of thumb is different socket for each
  protocol (UDP, TCP, ETC...) and _also_ different socket for each different server you are communicating with :
  ex: epfl.ch vs ethz.ch

- **Slow start** : Is still exponential ^^
- **Fast retransmit** : Can be very important in HTTP SEQ-type exercises. **Without** : Need timeout to retransmit
  (hence usually takes forever), **With** : Needs 3 (Convention, but can change in some exercises) ACKs with wrong
  SEQ number to retransmit

## Interesting illustrations :

Here are other little files with more details on specific but important subjects, with good illustrations on
the way these concepts work

- Go-Back-N vs Selective repeat details / Pros and cons : [more details on gbn and selective repeat]
- Basics of HTTP communication with SEQ numbers : [more details on SEQ numbers and related delays]


[more details on gbn and selective repeat]: details/gbn_vs_selective_repeat.md
[more details on SEQ numbers and related delays]: details/http_seq_delays.md

[midterm2017-solved]: resources/midterm2017-solved.pdf
[midterm2018-solved]: resources/midterm2018-solved.pdf
[midterm2019-solved]: resources/midterm2019-solved.pdf
