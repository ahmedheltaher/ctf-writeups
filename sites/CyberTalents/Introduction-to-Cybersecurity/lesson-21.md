# Lesson 21: Netcat

> Lesson Link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/21-netcat](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/21-netcat)*

## Introduction

Netcat is a tool that can be used to read and write data across network connections, using TCP or UDP protocol. It can be used to send and receive data from a port, or to connect to a port and send data to it. It can also be used to create a TCP or UDP server.

## Challenge

> Name:\
> *Cypher Anxiety*

---

> Description:\
> *An image was leaked from a babies store. the manager is so annoyed because he needs to identify the image to fire charges against the responsible employee. the key is the md5 of the image*

## Solution

In this challenge we are given an `pcap` file, and we need to find the image that was leaked.

We can use `wireshark` to open the `pcap` file, and then we can go `Statistics` -> `Conversation` -> `TCP` to see the TCP conversations.

We can see that there is a conversation between the employee who leaked the image and the other one, the conversation says:

```diff
-Hey bro
+Sup supp, are we ready
-yeah, u got the files?
+yes but i think the channel is not secured
-the UTM will block the file transfer as the DLP module is active
+ok we can use cryptcat
-ok what the password then
+let it be P@ssawordaya
-hhh, ok
+listen on 7070 and ill send you the file , bye
-bye
```

We can see that the employee used `cryptcat` to send the image, and the password is `P@ssawordaya`.

We can use `nc` to connect to the port `7070` and send the password `P@ssawordaya` to get the image.

First we need to filter the packets by `tcp.port == 7070` to see the packets that are sent to the port `7070`.

Then `Follow` -> `TCP Stream` to see the TCP stream.

Convert to original data and save it to a file, in me case I saved it to `encrypted_image`.

Lets run `cryptcat` reverse mode to decrypt the image:

```bash
cryptcat -k P@ssawordaya -l -p 7070 > decryptData
```

Then we can run `nc` to connect to the port `7070` and send the password `P@ssawordaya` to get the image.

```bash
nc localhost 7070 < encrypted_image
```

Now we can open the `decryptData` file and we can see the image. this is the image:

![image](../../../assets/CybertTalents/Cypher-Anxiety/decryptData)

How cute!

The flag is the md5 of the image. we can use `md5sum` to get the md5 of the image.

```bash
cat decryptData | md5sum
```

And We get the flag

## Flag

> 3beef06be834f3151309037dde4714ec

## References

- [https://en.wikipedia.org/wiki/Netcat](https://en.wikipedia.org/wiki/Netcat)

- [https://www.kali.org/tools/cryptcat/](https://www.kali.org/tools/cryptcat/)
