
Switch power on list

1. The switch loads a power-on-self-test  (POST) i ROM.
2. Next the switch loads the boot load software
3. The boot loader performs low-level  CPU initialization.
4. The boot loader initializes the flash file system on the system board.
5. Finally, the boot loader locates and loads a default IOS operating software image into memeory and gives control of the switch over to the IOS.

Half-duplex: Kan inte skicka och ta emot samtidigt
Full-duplex: Kan skicka och ta emot samtidigt
Vissa switchar klarar inte av Full-duplex.

Configurerar mest bara undantag.

Auto-MDIX känner av automatiskt vilket typ av kabel som går mellan olika enheter, crossover och straight.

CRC: Kollar så att datan är samma som den ska vara. Får man CRC så är datan skadad och inte är som den ska.

Ingress: Entering the interface
Egress: Leaving the interface

Store-and-forward
Cut-through forwards a frame as soon as the the destimation mac address is determend.

Preamble 8 bytes
Destination mac address 6 bytes
Source mac address 6
Type 2 bytes

När det finns mer än en enhet som kör half-duplex så finns det nu risk för kollision.

Vlan - Router
802.1Q enkapsulerings metod
