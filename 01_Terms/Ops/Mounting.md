--- 
tags: [#ops]
created: 12-09-2025
--- 
## 🔹 Definition / Formula
````
sshfs
````

## 🔹 Explanation (in my words)
Mounting a private node's storage with **SSHFS** means to make a remote directory on your private node appear and behave like a local folder on your computer. It essentially creates a live link where you can access, read, and write files on the remote location as if they were physically stored on your machine. This process is like plugging in a remote hard drive, allowing you to stream data over a secure SSH connection without copying it locally.

## 🔹 Components
- **Private node**: A remote server or machine where the original data and directory are located.
    
- **Compute node**: The local machine where you want to access the remote directory.
    
- **SSHFS (SSH File System)**: A file system client that enables you to mount a remote directory using the SSH protocol.
    
- **`/pool2/ritter2/serli`**: An example of the local mount point—a directory on the compute node that will serve as the gateway to the remote directory.

## 🔹 Context 
- Mounting is a core concept in **computer science**, particularly in **distributed systems** and **system administration**. It's used whenever you need to seamlessly access files from a remote server, network drive, or cloud storage as if they were local. This is common in **data science** and **machine learning** when working with large datasets stored on a central server, as it avoids the need to copy massive amounts of data back and forth.

## 🔹 Related
- [[SSH (Secure Shell)]] - [[Network File System (NFS)]] - [[File Transfer Protocol (FTP)]]

## 🔹 Examples / Applications
- Example code here 

## 🔹 Source 
- https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh