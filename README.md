# 2a_Stop_and_Wait_Protocol

## Developed By : SRIHARAN JV
## Register No  : 212223100054


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
# Client.py:
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

# server.py:
```
    import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT:
# Client :
![321844457-342905ca-15ca-46fd-a544-a5cd5021b69f](https://github.com/sriharan23000516/2a_Stop_and_Wait_Protocol/assets/139841769/9fa681a2-d9ab-42b4-b914-48f6b357439b)


# Server :
![321844475-92c0527e-e882-4b0a-abd3-2651c406fe89](https://github.com/sriharan23000516/2a_Stop_and_Wait_Protocol/assets/139841769/2005960c-c1c8-4f25-bd25-3a2d84d8adda)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
