# Ex No:4.Execution_of_NetworkCommands
# Name - Rabi baskar praburajan
# Reg no - 212224040257
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## Program
# client.py
```
import socket

from pythonping import ping 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5)
c,addr=s.accept()

while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```

# server.py
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```

## Output
# client.py
<img width="766" height="121" alt="image" src="https://github.com/user-attachments/assets/d869b1c4-5e31-4916-8009-cd79a129cd56" />

# server.py
<img width="806" height="318" alt="image" src="https://github.com/user-attachments/assets/0ae527f1-7eb2-4260-b94d-66942b00c5af" />

## Result
Thus Execution of Network commands Performed 
