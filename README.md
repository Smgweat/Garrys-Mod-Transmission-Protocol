# Garrys-Mod-Transmission-Protocol
A (hopefully) simplistic and functional two-wire based transmissions protocol for use with Expression-2

The following is a definition of the structure of packets in the GTP (Gmod Transmission Protocol)

PACKET

    HEADER
        Purpose
            Hold information regarding the packet's purpose

    Contents
        Size ( 8 bits )
        Datatype( 8 bits )
        Source( 8 bits )
        Destination( 8 bits )

    BODY
        Purpose
            Hold the information you are transferring
        
        Types
            String [Datatype 0]
                Holds a compressed string (See compression protocol)
                Each byte is a character which is concatenated with the rest of the body to form a single string.
            Integer [Datatype 1]
                Holds a string of Integer
                Each group of 4 bytes represents one 32-bit integer
            Vector [Datatype 2]
                Holds a string of vectors
                Each group of 12 bytes represents one 3-vector, with each section of 4 being an integer
