

# Super Useful Recap for Violent, Intense and Vile Exam
## (S.U.R.V.I.V.E for short)

*Click* sur la molette de la souris pour ouvrir une page dans un nouvel onglet. Je dirais que la façon optimale
d'utiliser ce doc une fois l'examen découvert c'est, pour chaque question, d'aller voir 
dans la [Lookup table](#lookup-table-) quel ressource(s)
y correspond(ent), de l'/les ouvrir dans un nouvel onglet (pour pouvoir rapidement revenir sur cette
page une fois la question finie). Si on ne comprend pas un terme ou que la correction de la ressource n'est pas compréhensible, 
revenir sur cette page et chercher dans les autres parties : Abréviations, Delay recap, Miscellaneous notes, illustrations...

Aller voir [Miscellaneous notes](#miscellaneous-notes-) 
et [Useful Conceptual Illustrations](#interesting-illustrations-) avant de commencer pour garder ça en tête.

## Summary

1. [Lookup Table](#lookup-table-): Lie chaque sujet/exercice type avec un/des corrigé(s)
2. [Abbreviations](#abbreviations-): Lie des abréviations à leur signification ainsi que leur description
3. [Quick Delay recap](#quick-delay-recap-): Récapitulatif rapide du calcul des delays
4. [Miscellaneous notes](#miscellaneous-notes-): Notes diverses
5. [Useful Conceptual Illustrations](#interesting-illustrations-): Si tu es quelqu'un qui aime le visuel, des illustrations
utiles sur certains concepts

## Lookup table :
| Subject | Details | File name | Problem | Question(s) | Details/Note |
|:-------:|---------|:---------:|:-------:|:---------:|--------------|
|HTTP |HTTP Messages and proxy Cache + DNS Resolution | [midterm2018-solved] | 3 | 1.b, 2, 3, 4 | When DNS was resolved, proxy directly SYN to socket without going back to localhost |
|HTTP |HTTP Messages and Proxy Cache, less interesting| [midterm2019-solved] | 2 | 1, 2         | When authoritative DNS server is not the first contacted
|HTTP|HTTP Messages, DNS recursive resolution w\ proxy|[midterm2017-solved]|2|1| Recursive is d1 <=> d2 <=> d3, iterative is the other one|
|HTTP |GBN vs Sel. Rep.  |[midterm2017-solved]|3|1, 2|There are pros for go-back-n too|
|HTTP |Reliable data transfer elements|[midterm2017-solved]|3|3, 4|Different configurations of network, choose the right RDT elements for each|
|HTTP |Evolution of Window Congestion Size|[final2019-solved]|4|1|Working with slow start and congestion avoidance|
|HTTP |What happens when we press enter on URL|[homework2-solved]|all| - |DNS and HTTP resources resolution
|Attack|Http Persa attack|[midterm2017-solved]|2|3, 4| |
|LAB-related|Command|[midterm2019-solved]|2|3|`DIG` command question| 
|Delay|Basics for computing delays|[homework1-solved]|all| - |Transmission, Throughput, Delay, With or Without switches, etc...|
|Delay|Exotic Delay computing for P2P/Server and Switches|[midterm2019-solved]|4|1, 2, 3, 4|

## Abbreviations :

#### HTTP :
|Abbreviation | Meaning | Description |
|:-----------:|:-------:|------------|
**RTT** | Round trip time | Time for a *small* packet to go to destination, then for the *small* response to come back. Can be used with most of the packet exchanged in an HTTP SEQ-type exercise because MSS is usually small|
**MSS** | Maximum Segment Size | Usually the size of each segment sent in the HTTP SEQ-type exercises, it is dictated by network's properties|
**ACK** | Acknowledgement | In response to your request, if it was received, in some exercises can be replaced with "**200 OK**" (for example in Message SRC-DEST tables to fill)|
**GBN** | Go-Back-N | The receiver has a window of **size 1**, it's willing to accept only one SEQ at a time and discards anything else. Sender retransmits all sent after last ACKed segment, because it knows receiver has discarded them all. ACKs are **Cumulative** means if there is **ACK 143**, all BITS from 0 to 143 were correctly acknowledged |
**SR** | Selective Repeat | Receiver has window size of K, ACKs are **Selective** means that if ACK 10, segment 10 has been ACKed. If lost, only the lost segment is retransmitted|
**RDT**| Reliable Data Transfer (elements) | Includes Checksum, (Pipelining), SEQ numbers, ACKs, timeouts... |
**FRR** | Fast Retransmit and Recovery | Retransmit : 3 ACKs = retransmit, Recovery : if receiver got out of order segment, send duplicate ACKs|
#### Delays :
|Abbreviation | Meaning | Description |
|:-----------:|:-------:|------------|
**BDP** | Bandwidth Delay Product | `BDP = R · d_propagation`, maximum nb of bits that can transit on the link at any point in time|
**S&F** | Store & Forward | For packet switches, means it doesn't retransmit the file until the very last bit has arrived in the queue

## Quick delay recap :

<img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/img/transmission_delay.png?raw=true" alt="transmission_delay" width="50%"/>

<img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/img/propagation_delay.png?raw=true" alt="propagation_delay" width="50%"/>

When there is a packet switch in the middle of two links, otherwise just remove everything
from "+ queuing delay" to the end

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
- What happens at a packet switch EXACTLY : [more details on packet switches]

[more details on packet switches]: details/packet_switching.md
[more details on gbn and selective repeat]: details/gbn_vs_selective_repeat.md
[more details on SEQ numbers and related delays]: details/http_seq_delays.md

[midterm2017-solved]: resources/midterms/midterm2017-solved.pdf
[midterm2018-solved]: resources/midterms/midterm2018-solved.pdf
[midterm2019-solved]: resources/midterms/midterm2019-solved.pdf
[final2019-solved]: resources/finals/final2019-solved.pdf
[homework1-solved]: resources/homeworks/hw1-solved.pdf
[homework2-solved]: resources/homeworks/hw2-solved.pdf
