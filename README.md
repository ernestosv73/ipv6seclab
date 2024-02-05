# IPv6 Security Lab
This test laboratory aims to provide a network topology based on Containerlab that allows you to understand the operation of the protocols involved in the IPv6 address autoconfiguration process.
To mitigate one of the security issues of IPv6 SLAAC, this scenario provides an example of configuring Router Advertisement Guard based on an IPv6 filter ACL.


## Description

The lab consists of an Nokia SR Linux router node connected to an Nokia SR Linux node configured as a switch. Three host nodes are also connected to the switch:
PC1 and PC2: Kali Linux OS. Image based on kali-rolling with packages net-tools, iproute2, ipv6toolkit and Thc-Ipv6.
PC3: Alpine Linux with net tools.

Nokia SRL Linux Router General Config:
* Eth1/1.0 IPv6 static global unicast address (2001:db8:aaaa:1::1/64) with Router Advertisement, (advertised prefix: 2001:db8:aaaa:1::/64).

Nokia SRL Linux Switch General Config:
* A network instance type mac-vrf is created with the name "lanswitch". Interfaces eth1 to eth4 are configured as type bridged and associated with this net instance.
* An IPv6 ACL filter is configured, named "ipv6ra". The action is specified as drop, with logging set to true. The filter matches packets with IPv6 header field "next-header:58", "icmp6 type:134", "code:0"
* The configured ACL is attached to the eth2 and eth4 interfaces for incoming traffic. 
## Getting Started

### Dependencies

* Describe any prerequisites, libraries, OS version, etc., needed before installing program.
* ex. Windows 10

### Installing

* How/where to download your program
* Any modifications needed to be made to files/folders

### Executing program

* How to run the program
* Step-by-step bullets
```
code blocks for commands
```

## Help

Any advise for common problems or issues.
```
command to run if program contains helper info
```

## Authors

Contributors names and contact info

ex. Dominique Pizzie  
ex. [@DomPizzie](https://twitter.com/dompizzie)

## Version History

* 0.2
    * Various bug fixes and optimizations
    * See [commit change]() or See [release history]()
* 0.1
    * Initial Release

## License

This project is licensed under the [NAME HERE] License - see the LICENSE.md file for details

## Acknowledgments

Inspiration, code snippets, etc.
* [awesome-readme](https://github.com/matiassingers/awesome-readme)
* [PurpleBooth](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2)
* [dbader](https://github.com/dbader/readme-template)
* [zenorocha](https://gist.github.com/zenorocha/4526327)
* [fvcproductions](https://gist.github.com/fvcproductions/1bfc2d4aecb01a834b46)
