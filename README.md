# OpenVPN Tunnel Guarantee
 A simple bash script for Linux, which, given the IP address of a current tun-based OpenVPN connection on port 1197, manipulates the Linux iptables to ensure that no traffic is permitted outside of this tunnel. Prevents the need for a VPN killswitch and gives peace of mind. Tested on Ubuntu 17.04.

 
 Usage instructions:
 
 1) Initialise your OpenVPN connection on a tun interface.
 
 2) Note the IP address of the connection from the stdout - you should see something like the following "Peer Connection Initiated with [AF_INET]ww.xx.yy.zz:1197"
 
 3) Open a new terminal and navigate to the folder where the tunnel script is stored

 4) Run the script with "sudo ./tunnel ww.xx.yy.zz" where ww.xx.yy.zz is the IP address from step 2.
 
 5) When you are finished with your VPN connection, or it drops out and you need to re-enable normal traffic, type "sudo iptables -F" to undo the effect of the script.