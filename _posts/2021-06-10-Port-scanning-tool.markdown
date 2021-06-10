---
layout: post
title:  "Port Scanning Tool: finding-PORTy"
date:   2021-06-10 6:00:00 +0800
categories: coding
---

# What is it?
finding-PORTy is a proof of concept fully functional port scanning tool designed to check open ports, check live host in a network, stealth scans, and keep activity data for later use. I wrote it on Python 3 so the codebase is supposed to be easily understandable and modified for further use. 

here's what it looks like
```bash
    |\    o
    |  \    o
|\ /    .\ o
| |       ( ======[finding-PORTy v1.]======
|/ \     /
    |  /
     |/
                    


===[OPTIONS]=== 
 [1] Scan Open Ports 
 [2] Ping Sweep Live Host (Loud) 
 [3] TCP Scan (Stealth) 
 [4] Show Activities 
 [5] Remove History
 [0] Exit
Action: 
```

# What's the Souce?
souce: [https://github.com/AdrianDucao/finding-PORTy](https://github.com/AdrianDucao/finding-PORTy)

# Conclusion
Learning curve is a minor setback with [Socket Module](https://docs.python.org/3/library/socket.html?highlight=socket#module-socket), read Python 3 Documentations [OS Documentation](https://docs.python.org/3/library/os.html?highlight=os#module-os), [CSV documentation](https://docs.python.org/3/library/csv.html?highlight=csv), the [python3 network programming](https://www.tutorialspoint.com/python3/python_networking.htm), and some stack overflow for errors really helped.


Happy Coding.