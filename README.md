cs525-SimpleVirtualRouter
=========================

phase1- A project that implements a simple and functional IP Router that routes real network traffic.


Virtual Network Lab (VNL) is an educational platform where students can gain hands-on experience on network protocols by programming routers and hosts. It is inspired by Stanford VNS. VNL is comprised of two components: (1) The VNL services which run in a set of virtual machines on postino.cs.arizona.edu, and (2) VNL soft-hosts such as your router. The service intercepts packets on the network, forwards the packets to the soft-hosts, receives packets from the soft-host and injects them back into the network. The soft-hosts are run locally by the students as regular user processes and connect to the service via ssh tunnels. Clients, once connected to the server, are forwarded all packets that they are supposed to see in the topology. The soft-hosts can manipulate the packets in any way they wish, generate responses based on the packets, or make routing decisions for those packets and send the replies back to the service to place back onto the network.
