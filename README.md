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
## PROGRAM - ARP
```
NAME : Jude Clement Jose G

REGISTER NUMBER : 212224230109
```
## CLENT:
```
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
```
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 ip=input("Enter logical Address: ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode())
```
## OUPUT -ARP
## CLIENT:
<img width="960" alt="3ac" src="https://github.com/user-attachments/assets/cbba22a0-65d7-4327-aec8-6d0d2600fe18">

## SERVER:

<img width="960" alt="3as" src="https://github.com/user-attachments/assets/e67b9840-8e03-4435-a29e-96a45cac76ac">

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
