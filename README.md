THIS IS NOT MY WORK!!!

Centralized here for my own personal convenience. 

Full credit given to the authors: https://cs.baylor.edu/~donahoo/practical/CSockets/textcode.html

Please support them [here](https://www.amazon.com/TCP-IP-Sockets-Practical-Programmers/dp/1558608265/ref=sr_1_4?crid=38KQE65IUUO8P&dib=eyJ2IjoiMSJ9.ESfQXWrb99bO19BPCyRzmhU2orSoEJVnLB0hbOF5x-wjFqI3BmlgRYRsmJv15pZIuR9cFLh7B7bpm2SLlnv6V69kAip3bNcbBG6LLEMLPWBkj-aXfhFXGUuVBv4ULFIWsSEZU5lmCr7Fg9hQqBaywNO1F_oCFcwHTEZaYmhTVsEA0QJvAt2dSu2R4K1gfShXRBoWKKpjq4drTpST1PxgzoI_H5QsxZv8KUMvjFoNWVzB3MHtQQWlBcxfREsL4EMqZk5bHcjdkOEY1XgevPkRSwe6ULhA_4zFZD_-jKfN5cY.T2W20i0a3EI0YE72j40Qpo8UVX3HrtU78UlmqTCIx90&dib_tag=se&keywords=tcp%2Bsockets%2Bin%2Bc&qid=1794159599&sprefix=tcp%2Bsockets%2Bin%2B%2Caps%2C203&sr=8-4&th=1)

---

Below is the example source code from "__TCP/IP Sockets in C: Practical Guide for Programmers" by Michael J. Donahoo and Kenneth L. Calvert__. 

![Describe the image here](https://cs.baylor.edu/~donahoo/practical/images/cpractical.gif)

This book can be ordered at your favorite local bookstore or online. [Official Book Website](http://www.mkp.com/books_catalog/catalog.asp?ISBN=1-55860-826-5)

Disclaimer: The purpose of this book is to provide general information about network programming as of the book's publication date. The authors have included sample code that is intended for the sole purpose of illustrating the use of the sockets API. Neither the authors nor the publisher are aware of any third party patents or proprietary rights that may cover any sample of any kind. The authors and the Publisher DISCLAIM ALL EXPRESS AND IMPLIED WARRANTIES, including warranties of merchantability and fitness for any particular purpose. Your use or reliance upon any sample code or other information in this book will be at your own risk. No one should use any sample code (or illustrations) from this book in any software application without first obtaining competent legal advice.

Example code:

- TCPEchoClient.c
- DieWithError.c
- TCPEchoServer.c
- HandleTCPClient.c
- UDPEchoClient.c
- UDPEchoServer.c
- SigAction.c
- UDPEchoServer-SIGIO.c
- UDPEchoClient-Timeout.c
- TCPEchoServer-Fork.c (without SIGCHLD)
- TCPEchoServer-Fork-SIGCHLD.c (with SIGCHLD)
- TCPEchoServer.h
- CreateTCPServerSocket.c
- AcceptTCPConnection.c
- TCPEchoServer-Thread.c
- TCPEchoServer-ForkN.c
- TCPEchoServer-Select.c
- BroadcastSender.c
- BroadcastReceiver.c
- MulticastSender.c
- MulticastReceiver.c
- ResolveName.c
- ResolveService.c

Generally, compilation is as follows:

Linux:
```
gcc -o TCPEchoClient TCPEchoClient.c DieWithError.c
```
Solaris:
```
gcc -o TCPEchoClient TCPEchoClient.c DieWithError.c -lsocket -lnsl
```
Both: Add `-lpthread` to both Linux and Solaris for the threads example

Note for older machines (e.g., SVR4 variants such as Solaris 2.5 and before): A few more include files may be necessary. 

If you get compile errors about u_short, try editing the include files as follows (**order matters**):
```
#include <stdio.h>      /* for printf() and fprintf() */
#include <sys/types.h>  /* for Socket data types */
#include <sys/socket.h> /* for socket(), connect(), send(), and recv() */
#include <netinet/in.h> /* for IP Socket data types */
#include <arpa/inet.h>  /* for sockaddr_in and inet_addr() */
#include <stdlib.h>     /* for atoi() */
#include <string.h>     /* for memset() */
#include <unistd.h>     /* for close() */
```
