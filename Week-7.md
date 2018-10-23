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
###### *Answear case 1*
Случай 1
Поскольку ПК подключены к сети, мы можем предположить, что интернет-протоколы имеют дело с различиями в сетях. Но компьютеры могут иметь разные аппаратные средства - поэтому нам приходится иметь дело с различиями в представлении элементов данных в запросах и ответах от клиентов к объектам. Общий стандарт будет определен для каждого типа элемента данных, который должен быть передан между объектом и его клиентами. На компьютерах могут работать разные операционные системы, поэтому нам нужно иметь дело с различными операциями для отправки и получения сообщений или для выписки вызовов. Таким образом, на уровне Java / C ++ будет использоваться общая операция, которая будет переведена на конкретную операцию в соответствии с текущей операционной системой. У нас есть два разных языка программирования C ++ и Java, они используют разные представления для структур данных, таких как строки, массивы, записи. Общий стандарт будет определен для каждого типа структуры данных, который должен быть передан между объектом и его клиентами, и способом перевода между этой структурой данных и каждым из языков. У нас могут быть разные исполнители, например. один для C ++ и другой для Java. Им необходимо будет согласовать общие стандарты, упомянутые выше, и документировать их.
###### *answear case 1*
As the PCs are joined to a web, we can assume that Internet protocols deal with differences in networks. But the computers may have different hardware - therefore we have to deal with differences of representation of data items in request and reply messages from clients to objects. A common standard will be defined for each type of data item that must be transmitted between the object and its clients. The computers may run different operating systems, therefore we need to deal with different operations to send and receive messages or to express invocations. Thus at the Java/C++ level a common operation would be used which will be translated to the particular operation according to the operating system it runs on. We have two different programming languages C++ and Java, they use different representations for data structures such as strings, arrays, records. A common standard will be defined for each type of data structure that must be transmitted between the object and its clients and a way of translating between that data structure and each of the languages. We may have different implementors, e.g. one for C++ and the other for Java. They will need to agree on the common standards mentioned above and to document them.
###### *answear case 2*
Случай 2
Чтобы добавить объект BLOB в существующую открытую распределенную систему, стандарты, упомянутые в ответе на упражнение 1.7, уже должны быть согласованы для распределенной системы. Перечислите их еще раз:
распределенная система использует общий набор протоколов связи (возможно, интернет-протоколы).
 он использует определенный стандарт для представления элементов данных (для решения гетерогенности аппаратного обеспечения).
Он использует общий стандарт для операций передачи сообщений (или для вызовов).
 Он использует независимый от языка стандарт для представления структур данных.
Но для открытой распределенной системы стандарты должны быть согласованы и задокументированы до реализации объекта BLOB. Разработчики должны соответствовать этим стандартам. Кроме того, должен быть опубликован интерфейс к объекту BLOB, так что когда он будет добавлен в систему, доступ к нему смогут получить как существующие, так и новые клиенты. Публикация стандартов позволяет частям системы внедряться различными поставщиками и работать вместе.
###### *answear case 2*
Case 2
To add the BLOB object to an existing open distributed system, the standards mentioned in the answer to “case 1” must already have been agreed for the distributed system To list them again:
the distributed system uses a common set of communication protocols (probably Internet protocols).
 it uses an defined standard for representing data items (to deal with heterogeneity of hardware).
It uses a common standard for message passing operations (or for invocations).
 It uses a language independent standard for representing data structures.
But for the open distributed system the standards must have been agreed and documented before the BLOB object was implemented. The implementors must conform to those standards. In addition, the interface to the BLOB object must be published so that when it is added to the system, both existing and new clients will be able to access it. The publication of the standards allows parts of the system to be implemented by different vendors and to work together.
###### *Answear case 3*
Случай 3
Каждый запрос на доступ к защищенной операции должен содержать идентификатор пользователя, делающего запрос. Проблемы:
 определяя идентификаторы пользователей. Использование этих идентификаторов в списке пользователей, которым разрешен доступ к защищенным операциям при реализации объекта BLOB. И в сообщениях запроса.
 гарантируя, что предоставленная идентификация исходит от пользователя, которого он хочет быть, а не другого пользователя, претендующего на роль этого пользователя.
не позволяя другим пользователям воспроизводить или подделывать сообщения запроса законных пользователей.
информация, возвращаемая в результате защищенной операции, должна быть скрыта от неавторизованных пользователей. Это означает, что сообщения, содержащие информацию, должны быть зашифрованы в случае, если они перехвачены неавторизованными пользователями.
###### *answear case 3*
Each request to access a protected operation must include the identity of the user making the request. The problems are:
 defining the identities of the users. Using these identities in the list of users who are allowed to access the protected operations at the implementation of the BLOB object. And in the request messages.
 ensuring that the identity supplied comes from the user it purports to be and not some other user pretending to be that user.
preventing other users from replaying or tampering with the request messages of legitimate users.
the information returned as the result of a protected operation must be hidden from unauthorised users. This means that the messages containing the information must be encrypted in case they are intercepted by unauthorised users.



