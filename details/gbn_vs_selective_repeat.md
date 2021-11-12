# Details on GBN vs Sel. Rep. :

Selective Repeat is expected to achieve higher sender utilization and throughput than Go-Back-N
when there are few, independent packet losses.
Go-Back-N is expected to achieve higher sender utilization and throughput than Selective Repeat
when there is bursty loss on the reverse channel (many ACKs get lost back to back).
([midterm2017-solved], Problem 3, Question 3)

### Situation where GBN wins :

<img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/img/gbn_vs_sr_gbn_wins.png?raw=true" alt="gbn_vs_sr" width="50%"/>

### Situation where Selective Repeat Wins :

<img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/img/gbn_vs_sr_sr_wins.png?raw=true" alt="gbn_vs_sr" width="50%"/>


[midterm2017-solved]: ../resources/midterms/midterm2017-solved.pdf