# From Socket to Socket.io

Minchiuan Gao 2015-Oct

### 0. Client-Server Model And Network

all network applications are based on the same basic programming model, have similar overall logical structures, and rely on the same programming interface.(1)

Every network applicaiton is based on the client-server model.
With this model, an application consists of a *server* process and one or omre *client* process.

1. When a client needs service, it initiates a transaction by sending a request to the server. For example, when a Web browser needs a file, it sends a request to a Web server.
2. Theserverreceivestherequest,interpretsit,andmanipulatesitsresourcesin the appropriate way. For example, when a Web server receives a request from a browser, it reads a disk file.
3. The server sends a response to the client, and then waits for the next request. For example, a Web server sends the file back to a client.
4. Theclientreceivestheresponseandmanipulatesit.Forexample,afteraWeb browser receives a page from the server, it displays it on the screen.

[!Image of server four process]

**Noticw**: The clients and servers and process and not machines.  A single host could run many servers or clients, and a server or client cloud run at different hosts too.

**When regradless of the mapping of clients and servers to hosts. The client-server model is the same**.

To a host, a network is just another I/O device that servers as a source and sink for data.

### The sockets Interface

The *sockets interfaces* is a set of functions that are userd in conjunction with the Unix I/O functions to build network applications. It has been implements on the most modern systems, including all Unix variants, Windows.

			|	Client	|		|	Server	|	
------------|-----------|-------|-----------|----------
openClent	| socket	|							|	socket	|	openListen
			|			|							|	bind	|	
			|			|							|	linsten	|	
			|connnet	|--Connection requests --->	|	accept	|	<-
------------|rio written|-------------------------->|rio readline| loop for
			|rio readlineb|<------------------------|rio written | awaiting
			| close		|-- -- -- EOF -- -- -- ---->|rio readlineb| next client


(1). CSAPP
