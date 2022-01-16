1) Change config file: sudo nano /etc/inetd.conf
2) Input 2 string in the end: 
# HTTP proxy
1060 dgram udp wait nobody usr/bin/nc echo -n "foo" | nc -u localhost 1065
3) Save file and exit.
4) Open two terminals:
in the first input:sudo nc -l localhost 1065
"-l" means that this port listens. 
in the second input: sudo nc localhost 1060
Your port should be more than 1024, because <1024 is system port.
5) Write your msg in 1060 and your msg will appear in 1065.
