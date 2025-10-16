# Ex.No:1b  			IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME: PUGAZHALENTHI V
## REG NO : 212224100047


## Aim: 
To write a python program to perform sliding window protocol
## ALGORITHM:
ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program
PROGRAM:

SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
CLIENT
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
```
## OUTPUT:

## server.py

<img width="476" height="138" alt="Screenshot 2025-10-13 154335" src="https://github.com/user-attachments/assets/eac89f87-f52c-4965-8cc2-36da499ff2ac" />


## client.py

<img width="615" height="185" alt="Screenshot 2025-10-13 154325" src="https://github.com/user-attachments/assets/6dde34dd-2584-45f4-a572-e4e7cc35ebd9" />


 
## Result:
Thus the study of Socket Programming Completed Successfully
