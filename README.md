# Comp midterm net resources:

## Lookup table:
| Subject | Details | File name | Problem | Questions | Details/Note |
|---------|---------|-----------|---------|-----------|--------------|
|HTTP |HTTP Messages and proxy Cache + DNS Resolution | [midterm2018-solved] | 3 | 1.b, 2, 3, 4 | When DNS was resolved, proxy directly SYN to socket without going back to localhost |
|HTTP |HTTP Messages and Proxy Cache, less interesting| [midterm2019-solved] | 2 | 1, 2         | When authoritative DNS server is not the first contacted
|LAB-related|Command|[midterm2019-solved]|2|3|`DIG` command question| 
|HTTP|HTTP Messages, DNS recursive resolution w\ proxy|[midterm2017-solved]|2|1| |
|Attack|Http Persa attack|[midterm2017-solved]|2|3, 4| |

## Miscellaneous notes :

- **Pipelining** : Means technique in which multiple requests are written out to a single socket without waiting for the corresponding responses

- **Number of sockets** type of questions : Good rule of thumb is different socket for each 
protocol (UDP, TCP, ETC...) and _also_ different socket for each different server you are communicating with :
ex: epfl.ch vs ethz.ch

- **Slow start** : Is still exponential ^^






[midterm2017-solved]: resources/midterm2017-solved.pdf
[midterm2018-solved]: resources/midterm2018-solved.pdf
[midterm2019-solved]: resources/midterm2019-solved.pdf
