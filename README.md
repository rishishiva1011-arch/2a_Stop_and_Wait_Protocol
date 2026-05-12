# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
server.py
```
import socket
s=socket.socket()
s.bind(('localhost',8007))
s.listen(5)
c,addr=s.accept()
while True:
   i=input("Enter a data: ")
   c.send(i.encode())
   ack=c.recv(1024).decode()
   if ack:
    print(ack)
    continue
   else:
    c.close()
    break
```
client.py
```
import socket
s=socket.socket()
s.connect(('localhost',8007))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Received ".encode())
```
## OUTPUT

Server

<img width="405" height="153" alt="image" src="https://github.com/user-attachments/assets/002b8d57-aa9a-4b28-aec6-6349cb9360ca" />

Client

<img width="375" height="99" alt="image" src="https://github.com/user-attachments/assets/11d4bd12-2e65-4415-b144-53b6e24f7a1b" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
