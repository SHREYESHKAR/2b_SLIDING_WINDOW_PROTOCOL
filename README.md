# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
# SHREYESHKAR SEKAR
# 212224220099
## AIM : To write a python program to perform IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
SERVER.PY

import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True:    
    print(s.recv(1024).decode()) 
    s.send("acknowledgement recived from the server".encode())


```
```
CLIENT.PY

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
## OUPUT

https://private-user-images.githubusercontent.com/182351384/484947316-173767e3-b75c-4c9c-b860-5063fc5d9d5e.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NzM3NTM5MjAsIm5iZiI6MTc3Mzc1MzYyMCwicGF0aCI6Ii8xODIzNTEzODQvNDg0OTQ3MzE2LTE3Mzc2N2UzLWI3NWMtNGM5Yy1iODYwLTUwNjNmYzVkOWQ1ZS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwMzE3JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDMxN1QxMzIwMjBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1hMzMzZTllODg4YmFmMjhkY2ZkNGI2NjhlZDkyZGM0NWJkZTY4MjkxMWU1M2M4MTc4NzkxZDU1MTJhMzEyZWRjJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.rDPjCzlpL9mBgsrEesDVU3dE5PvtkdKtPzzE6k8FqF8



## RESULT
Thus, python program to perform IMPLEMENTATION OF SLIDING WINDOW PROTOCOL was successfully executed
