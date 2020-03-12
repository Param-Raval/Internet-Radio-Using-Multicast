# Internet-Radio-Using-Multicast

The objective of this project is to develop an internet radio by implementing multicast such that multiple users can listen to the same live-feed and even change the radio stations as they wish. We use the Any Source Multicast (ASM) model in which the messages are identified by the multicast group address alone. Several users can reside in the same multicast group, and nodes connected over the same group receive all the messages sent to that group.

The client will have the functionality to pause, play, and change station at will without losing synchronization with the live stream. The server can add new stations, delete stations, and add songs to each station.

Concepts:

-A TCP socket is used as a control channel and receiving station info from the server.
-Server sends multimedia over a UDP socket once the client is connected
-To enable multiple users/clients, we use threading which creates a new thread each time a client connects with the server
-The multicast reception stops and the thread is deleted once the client disconnects (pauses) with the server. A new thread is formed upon restarting.
