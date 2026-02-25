# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
CLIENT:
```
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
if ack:
 print(ack)
c.close()
```
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```
## OUPUT
Client
<img width="1632" height="133" alt="image" src="https://github.com/user-attachments/assets/07a2b036-7334-4be6-87cb-4902a59a43d3" />

Sever
<img width="1845" height="173" alt="image" src="https://github.com/user-attachments/assets/0b635b5e-7503-42af-96db-64cecbb4f882" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
