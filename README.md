# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

DATE :

AIM :

To write a python program to perform client server model.

ALGORITHM :

    Start the program.
    Get the frame size from the user
    To create the frame based on the user request.
    To send frames to server from the client side.
    If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
    Stop the program

CLIENT PROGRAM:

Developed By : Sindhuja P

Reg No : 212222220047

import socket

s=socket.socket()

s.bind(('localhost',8080))

s.listen(5)

c,addr=s.accept()

while True:

i=input("ENter a data:")

c.send(i.encode())

ack=c.recv(1024).decode()

if ack:

	print(ack)

	continue

else:

	c.close()

	break

SERVER PROGRAME:

import socket

s=socket.socket()

s.connect(('localhost',8080))

while True:

print(s.recv(1024).decode())

s.send("Recieved".encode())

CLIENT OUTPUT:

![image](https://github.com/Sindhuja9585/19CS406-EX-1/assets/122860624/c616e05d-40d9-4c01-ae5a-92f1d0a3f0b8)


SERVER OUTPUT:

![image](https://github.com/Sindhuja9585/19CS406-EX-1/assets/122860624/02098498-387e-4da0-8e22-846128cafb76)


RESULT:

Thus, python program to perform stop and wait protocol was successfully executed.
