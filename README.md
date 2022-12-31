<!--
*** Firewall-Packet-Filter
*** Packet Filter for FreeBSD Firewall
-->

# Firewall-Packet-Filter for FreeBSD.

How to enable PF on FreeBSD 12.1

1. Input this commmand:

   ```sh
   sysrc pf_enable=yes
   ```
2. Download the file "pf.conf" and upload in your-option-folder. 

NOTE: Please you need modificate the pf.conf PORTS for your PORTS or maybe you will be blocked.

3. Configure the rules with the pf.conf

   ```sh
   sysrc pf_rules=/your-option-folder/pf.conf
   ````
   
If you want logs you can active with this commands:

1. First command for enable Logs.

   ```sh
   sysrc pflog_enable=yes
   ```
   
2. Second command for specify archive destination logs.

   ```sh
   sysrc pflog_logfile=/var/log/pflog
   ```
      
# Start and Stop Firewall

a) Command for start Firewall:

   ```sh
   service pf start
   ```
   
b) Command for start Logs:

   ```sh
   service pflog start
   ```
   
c) Command for stop Firewall:

   ```sh
   service pf stop
   ```
   
d) Command for restart Firewall:

   ```sh
   serve pf restart
   ```

e) Command for check Firewall status:

   ```sh
   service pf status
   ```
   
# Specific commands for this Rules PF Archive:

1. Show all abusive hosts:

   ```sh
   pfctl -t abusive_hosts -T show
   ```
2. Delete all Banned Clients:

   ```sh
   pfctl -t abusive_hosts -T flush
   ```
3. Add one IP for Ban:

   ```sh
   pfctl -t abusive_hosts -T add IP
   ```
4. Delete one IP Banned:

   ```sh
   pfctl -t abusive_hosts -T del IP
   ```
   
