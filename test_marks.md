### 1. Лыгин: -  +  +-  +-  +-  -  +  +  +  +    6,5 * 2 = 13 баллов

### 2. Малыгин: -  +  +-  +-  +-  -  +  +  +  +    6,5 * 2 = 13 баллов

### 3. Мурина: +  +  +-  -  +  -  -  +  -  -    4,5 * 2 = 9 баллов

### 4. Пронина: +  +  +-  -  +  -  -  +  -  -   4,5 * 2 = 9 баллов


## Комментарии:

### 1. 

HTTP is an application protocol running at the application layer. There are several protocols layered on top of each other. The stack of layers is often depicted like this:

Application Layer -- e.g. HTTP

Transport Layer -- e.g. TCP

Internet Layer -- e.g. IP

Link Layer -- e.g. IEEE 802.2

The so-called OSI (Open Systems Interconnection) model defines seven layers. We’ll take a look at the application, transport, and Internet layers for the typical HTTP usage: HTTP, TCP, and IP. The layers below IP are the data link and physical layers. These are the layers that, e.g. implement Ethernet (Ethernet has a data link part and a physical part).

### 3.

Многие правильно указали, что адрес 45.128.131.185 относится к IPv4, но при этом неверно соотнесли длину адреса с версией IP.

4 байта = 4 * 8 бит 

1 байт (8 бит) - это восемь знаков в двоичной системе счисления <=> число от 0 до 2^8 - 1 = 255 в десятичной системе

Тогда, используя точку как разделитель, адрес длиной 4 байта можно записать в виде 4 десятичных чисел [0-255].[0-255].[0-255].[0-255], а это типичный вид адреса для IPv4.

### 5. 

HTTP метода UPGRADE в спецификациях нет

### 6.

In TCP, a connection is always established from one host to another. Hence, there are two different roles in connection setup: one end (e.g. the web server) is listening for connections, while the other end (e.g. our app) connects to the listening application (e.g. the web server). The server performs a so-called passive open – it starts listening. The client performs a so-called active open toward the server.

Connection setup happens through a three-way handshake. It works like this:

1. The client sends a SYN to the server with a random sequence number, A
2. The server replies with a SYN-ACK with an acknowledgment number of A+1 and a random sequence number, B
3. The client sends an ACK to the server with an acknowledgement number of B+1 and a sequence number of A+1

SYN is short for synchronize sequence numbers. Once data flows between both ends, each TCP segment has a sequence number. This is how TCP makes sure that all parts arrive at the other end, and that they’re put together in the right order. Before communication can start, both ends need to synchronize the sequence number of the first segments.

ACK is short for acknowledgment. When a segment arrives at one of the ends, that end will acknowledge the receipt of that segment by sending an acknowledgment for the sequence number of the received segment.

