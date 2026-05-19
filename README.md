# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
DEVELOPED BY P.DHARSHINI

REGISTER NUMBER:212225040071
```
CLIENT
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"}; 
while True: 
    ip=c.recv(1024).decode() 
    try: 
        c.send(address[ip].encode()) 
    except KeyError: 
        c.send("Not Found".encode())

SERVER
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter logical Address : ") 
    s.send(ip.encode()) 
    print("MAC Address",s.recv(1024).decode())
```

## OUPUT - ARP
CLIENT
<img width="1919" height="1079" alt="Screenshot 2026-05-19 101118" src="https://github.com/user-attachments/assets/e472ac56-98fc-44cd-a4eb-78de613e73e9" />

SERVER
<img width="1919" height="1079" alt="Screenshot 2026-05-19 101036" src="https://github.com/user-attachments/assets/14fe779c-ec6a-455b-a228-60f8aaf13764" />

## PROGRAM - RARP
```
CLIENT

import socket 
s=socket.socket() 
s.bind(('localhost',9000)) 
s.listen(5) 
c,addr=s.accept() 
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"}; 
while True: 
    ip=c.recv(1024).decode() 
    try: 
        c.send(address[ip].encode()) 
    except KeyError: 
        c.send("Not Found".encode())

SERVER
import socket 
s=socket.socket() 
s.connect(('localhost',9000)) 
while True: 
    ip=input("Enter MAC Address : ") 
    s.send(ip.encode()) 
    print("Logical Address", s.recv(1024).decode())
```
## OUPUT -RARP
CLIENT

<img width="1919" height="1079" alt="Screenshot 2026-05-19 101857" src="https://github.com/user-attachments/assets/ac2b3ea2-85e8-405d-84e2-98271691570d" />


SERVER

<img width="1919" height="1079" alt="Screenshot 2026-05-19 101929" src="https://github.com/user-attachments/assets/dbf7c364-a3da-42d4-9dca-4d72d8ec7a74" />

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
