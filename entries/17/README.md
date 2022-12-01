# Subnets to Network IP

IPv4 networks can be subdivided into smaller groups. The smaller network
groups are called subnets that share the same network ID but unique host
IDs.

Networks are allocated using a method called Classless Inter-Domain
Routing (CIDR). The CIDR notation is shown as a slash followed by an
integer to denote the number of bits that are reserved for the network
ID. The higher the CIDR prefix, the less host networks available.

To convert a subnet to network ID from 192.168.156.97/19:
* Represent /19 into 4 octets (32 bits) for IPv4 with 19 on bits.
  * 11111111.11111111.11100000.00000000
  * Since the first 2 octets are 1, the first two octets for
    198.168.156.97 remain the same.
  * So, we will have 192.168 so far.
  * To work out the third octet, we overlay 156 to the subnet mask and
    calculate and multiply both octets.
  * 156 as binary: 10011100
  * 11100000
  * 10011100
  * 10000000 -> decimal is 128
  * The third octet for the network ID is 128.
  * Therefore, the full network ID is 192.168.128.0
  * 0 being that the final octet from out subnet is 0.
  * We use the last 13 bits from 192.168.156.97 as our host ID.
  * This will be:
    * 11100.01100001
    * 28.97 -> Therefore, our host ID is 0.0.28.97
