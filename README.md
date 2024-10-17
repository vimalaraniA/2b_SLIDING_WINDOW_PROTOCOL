NAME : Vimala Rani A      
REG NO : 212223040240


## AIM  

To write a python program to perform sliding window protocol

## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

CLIENT :

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

SERVER : 

import socket               
s=socket.socket()                 
s.connect(('localhost',8000))               
while True:                          
    print(s.recv(1024).decode())                                
    s.send("acknowledgement recived from the server".encode())                 

## OUPUT

CLIENT :

![Screenshot 2024-09-10 082749](https://github.com/user-attachments/assets/4162c8df-180f-4ab0-a6d8-158307145e8f) 

SERVER :

![Screenshot 2024-09-10 082831](https://github.com/user-attachments/assets/01a0af4c-4b7b-45d9-b6d0-42fde97bae3e)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
