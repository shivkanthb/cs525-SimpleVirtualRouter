cs525-SimpleVirtualRouter
=========================

phase1- A project that implements a simple and functional IP Router that routes real network traffic.


Virtual Network Lab (VNL) is an educational platform where students can gain hands-on experience on network protocols by programming routers and hosts. It is inspired by Stanford VNS. VNL is comprised of two components: (1) The VNL services which run in a set of virtual machines on postino.cs.arizona.edu, and (2) VNL soft-hosts such as your router. The service intercepts packets on the network, forwards the packets to the soft-hosts, receives packets from the soft-host and injects them back into the network. The soft-hosts are run locally by the students as regular user processes and connect to the service via ssh tunnels. Clients, once connected to the server, are forwarded all packets that they are supposed to see in the topology. The soft-hosts can manipulate the packets in any way they wish, generate responses based on the packets, or make routing decisions for those packets and send the replies back to the service to place back onto the network.

Functionalities implemented: 
1. The router correctly handles ARP requests and replies.
2. The router responds correctly to ICMP echo requests.
3. The router correctly handles traceroutes through it (where it is not the end host) and to it (where it is the end host).
4. The router can successfully route packets between the gateway and the application servers.
5. The router maintains an ARP cache whose entries are invalidated after a timeout period (timeouts should be on the order of 15 seconds).
6. The router queues all packets waiting for outstanding ARP replies. If a host does not respond to 5 ARP requests, the queued packet is dropped and an ICMP host unreachable message is sent back to the source of the queued packet.
7. The router does not needlessly drop packets (for example when waiting for an ARP reply)
8. The router handles tcp/udp packets sent to one of its interfaces. In this case the router should respond with an ICMP port unreachable.

To do:
9. The router enforces guarantees on timeouts. Currently the stub code is event based. That is, code is executed each time a packet is received. This makest it hard to correctly enforce timeouts. For example, if the router is waiting for an ARP reply that doesn't come, it will have to wait for another packet to arrive before it can handle the timeout. Of course, if a packet never arrives, the timeout will never be serviced. You should implement a method of timing out ARP requests and ARP cache entries that can be guaranteed to function within a (relatively) fixed period, even if no more packets arrive at the router.
