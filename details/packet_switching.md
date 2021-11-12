# More details on packet switches :

- **Store and forward** : Does not forward/retransmit the packet until the very last bit of
  the packet has arrived in the queue
    - Typical flow : The first bits of the packet arrive in the switch, if there is no queue, wait for the very last 
  bit of the packet to arrive. Once the whole packet has entered the switch (At this point end of **queueing delay**),
  process it: (Beginning of **processing delay**), get the MAC address in the header of the packet and go in the 
  **Lookup MAC table** and then forward the packet (End of **processing delay**), pushing every bit onto the next link
      (**Transmission delay**)

<div style="display: flex; justify-content: center; justify-items: center; margin: 2%">
    <img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/gifs/store_and_forward.gif?raw=true" alt="transmission_delay" width="65%"/>
</div>

- **Cut through switching** (default) : Immediately after the receiving of the complete MAC header, get
the MAC address and starts pushing the packet onto the next link (There is a **Processing delay** and a 
**Transmission delay** but no **Queuing delay**)

<div style="display: flex; justify-content: center; justify-items: center; margin: 2%">
    <img src="https://github.com/WollfieGitHub/CompNetResources/blob/master/resources/gifs/cut_through_switching.gif?raw=true" alt="transmission_delay" width="65%"/>
</div>
