# 2a_Stop_and_Wait_Protocol 
 NAME:sharukesh.s
 REG NO :212224220095
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
 SERVER
  import socket

s = socket.socket()

s.bind(('localhost', 8000))

s.listen(1)

print("Server listening...")

c, addr = s.accept()

print("Connected:", addr)

while True:
    data = c.recv(1024)
    if not data: break
    msg = data.decode()
    print("Client:", msg)
    c.send(b"ACK")
    if msg.lower() == "exit": break

c.close()

s.close()


CLIENT
  import socket

s = socket.socket()

s.connect(('localhost', 8000))

while True:
    msg = input("Enter message for server: ")
    s.send(msg.encode())
    data = s.recv(1024).decode()
    print("Server:", data)

    if msg.lower() == "exit":
        break

s.close()

  
## OUTPUT
<img width="1915" height="1151" alt="Screenshot 2025-09-03 110548" src="https://github.com/user-attachments/assets/bd5df359-b35a-4836-8455-b4d44445030a" />
<img width="1919" height="1147" alt="Screenshot 2025-09-03 110608" src="https://github.com/user-attachments/assets/decc6bf7-c3d9-41a2-95a7-1ddfb49ef679" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
