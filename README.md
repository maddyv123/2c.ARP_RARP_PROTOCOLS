# 2c.SIMULATING ARP /RARP PROTOCOLS
## Name: Mathavan V
## Register No: 212223110026
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
# PROGRAM - ARP
## Client:
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
## OUPUT - ARP
![309004369-a9b8b4f9-7f2d-4760-8363-285529f8774c](https://github.com/820NaveenKumar208/2c.ARP_RARP_PROTOCOLS/assets/154746066/27af49ea-c8b1-4a8c-ba41-0e86809b0485)

## PROGRAM - RARP
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
```
## OUPUT -RARP
![309004910-33ddf5c6-98a3-4d8d-952c-4b685b37093a](https://github.com/820NaveenKumar208/2c.ARP_RARP_PROTOCOLS/assets/154746066/cd702c22-3588-4372-82d0-ab1071a45653)


## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
