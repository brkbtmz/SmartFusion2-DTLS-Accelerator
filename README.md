DTLS Acceleration on SmartFusion2

This repository contains files necessary to conduct experiments on the SmartFusion2 Security Evaluation Board for DTLS packet processing. These experiments use the board in conjunction with a Pmod NIC100 Ethernet interface.
Requirements

To set up and run the experiments, you will need:

    SmartFusion2 Security Evaluation Board
    Pmod NIC100 Ethernet module
    Network switch with port mirroring capability
    Two host machines:
        Sender: Sends DTLS packets to the SmartFusion2 board.
        Observer: Captures network traffic without affecting communication timing.

Setup
Hardware Setup

    Connect Pmod NIC100 to the SmartFusion2 Board.
    Connect the Sender, Observer, and SmartFusion2 Board to the network switch.
        Make sure the switch supports port mirroring.
        Configure port mirroring on the switch to mirror the traffic from the port connected to the SmartFusion2 Board to the port connected to the Observer.

Programming the SmartFusion2

    Use the .stp file from this repository to program the SmartFusion2 Security Evaluation Board. Follow the board's documentation for the programming steps.

Experiment

    Send DTLS packets from the Sender host to the SmartFusion2 Board.
        The board will process the DTLS packets and generate response messages.
    Monitor the communication using a network sniffer (e.g., Wireshark) on the Observer host. The Observer captures the traffic without affecting the timing of the communication between the Sender and the SmartFusion2 Board.

Notes

    The Observer host is used solely for packet capturing to ensure that it does not interfere with the real-time communication between the Sender and the SmartFusion2 Board.
    Ensure that the network sniffer is correctly configured on the Observer host to capture the mirrored traffic.
