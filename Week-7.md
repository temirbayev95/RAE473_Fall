# Distributed Systems and their Features
## Case Nr. 1
A server program written in one programming language (for example C++) provides the implementation of a BLOB (Binary Large Object) object that is intended to be accessed by clients that may be written in a different language (for example Java). The client and server computers may have different hardware, but all of them are attached to an internet.

###### *Question*
Describe the problems due to each of the five aspects of heterogeneity that need to be solved to make it possible for a client object to invoke a method on the server object.

## Case Nr. 2
###### *Let us contunue with a situation from Case Nr. 1*
An open distributed system allows new resource sharing services such as the BLOB object mentioned in Case Nr.1. 
to be added and accessed by a variety of client programs. 
###### *Question*
Discuss in the context of this example, to what extent the needs of openness differ from those of heterogeneity.

## Case Nr. 3
###### *We are working with a relevance to situation from Case Nr. 1 about BLOB*
Suppose that the operations of the BLOB object are separated into two categories – public
operations that are available to all users and protected operations that are available only to certain
named users. 
###### *Question*
State all of the problems involved in ensuring that only the named users can use a
protected operation. Supposing that access to a protected operation provides information that
should not be revealed to all users, what further problems arise?
