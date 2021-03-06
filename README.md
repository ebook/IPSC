##PROJECT: MotoTRB IPSC dissector
**This is a wireshark dissector for IP Site Connect as it is presented in:**  
https://github.com/n0mjs710/IPSC  
https://github.com/KD8EYF/OpenIPSC  
TS 102 361-1  
TS 102 361-2  
TS 102 361-3  


###HowTo:

**IPSC dissector in wireshark:**

- Download and build sources of a stable version of wireshark from www.wireshark.org
- Copy packet-ipsc.c to DIR/epan/dissectors/
- Modify DIR/epan/dissectors/Makefile.common to include packet-ipsc.c  

 packet-ipsec.c  
 packet-ipsc.c  
 packet-ipsi-ctl.c  

- Add call to IPSC in register.c  

 {extern void proto_register_ipsc (void); if(cb) (*cb)(RA_REGISTER, "proto_register_ipsc", client_data); proto_register_ipsc ();}

- go to DIR and build and install: make && sudo make install

![alt text][logo]
[logo]: https://github.com/BogdanDIA/IPSC/raw/master/IPSC_screenshot.png "Wireshark IPSC"
