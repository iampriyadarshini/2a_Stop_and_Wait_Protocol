# EX.NO:2a_Stop_and_Wait_Protocol
## NAME - PRIYADARSHINI K
## REG NO - 212224100046
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
## CLIENT
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
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

## SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
    
## OUTPUT
## CLIENT
<img width="487" height="355" alt="image" src="https://github.com/user-attachments/assets/5edc70d6-4d50-4e2d-8eea-3b748053b34f" />

## SERVER 
<img width="550" height="251" alt="image" src="https://github.com/user-attachments/assets/f70cc735-c345-4c58-a5b7-427e92287a82" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
