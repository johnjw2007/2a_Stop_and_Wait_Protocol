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
1. Client:
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
2. Server:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
print(s.getsockname()) 
print(s.recv(1024).decode()) 
s.send("acknowledgement recived from the server".encode())
```

## OUTPUT
1. Server:
![image](https://github.com/user-attachments/assets/345b66ec-af8b-4556-83f6-0da1c2618a61)
2.Client:
![image](https://github.com/user-attachments/assets/3cb36062-70cf-4823-b1d2-b66c98fa2510)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
