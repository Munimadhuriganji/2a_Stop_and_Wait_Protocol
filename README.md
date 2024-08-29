# NAME:GANJI MUNI MADHURI
# REFERENCE NUMBER:212223230060
## 2a_Stop_and_Wait_Protocol
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
# client.py
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
# server.py
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
     print(s.recv(1024).decode())
     s.send("Acknowledgement Recived".encode())
```
## OUTPUT
# client.py
![Screenshot 2024-08-29 102608](https://github.com/user-attachments/assets/81d8a286-0bfd-4c14-9cec-e55af1bdcf55)

# server.py
![Screenshot 2024-08-29 102556](https://github.com/user-attachments/assets/0a551e10-e0fd-4089-84bf-060b9febba22)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
