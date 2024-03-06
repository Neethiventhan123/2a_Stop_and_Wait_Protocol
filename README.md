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
```
## client.py
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

## server.py
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode()) 
```
## OUTPUT

## client output:
![Screenshot 2024-03-06 112626](https://github.com/Neethiventhan123/2a_Stop_and_Wait_Protocol/assets/148514848/a0837935-8458-4c5b-9edb-2c6c6c1d5d14)

## server output:
![Screenshot 2024-03-06 112650](https://github.com/Neethiventhan123/2a_Stop_and_Wait_Protocol/assets/148514848/3cd401be-e300-4b92-a3fa-1a36da6b8f65)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
