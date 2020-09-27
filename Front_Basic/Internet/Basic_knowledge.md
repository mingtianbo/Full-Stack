# Frontend Developer

## Internet

### How does the internet work?

The Internet works through a packet routing network in accordance with the Internet Protocol(IP), the Transport Control Protocol(TCP) and other protocols.

#### What's a protocol?

A protocol is a set of rules specifying how computers should communicate with each other over a network. For example, the *Transport Control Protocol* has a rule that if one computer sends data to another computer, the destination computer should let the source computer know if any data was missing so the source computer can re-send it. <strong>Or the *Internet Protocol* which specifies how computers should route information to other computers by attaching addresses onto the data it sends.</strong>

#### What's a packet?

Data sent across the Internet is called a *message*. Before a *message* is sent, it is first split in many fragments called *packets*. These *packets* are sent independently of each other. The typical maximum *packet* size is between 1000 and 3000 characters. The *Internet Protocol* specifies how messages should be packetized.

#### What's a packet routing network?

It is a network that routes *packets* from a source computer to a destination computer. The Internet is made up of a massive network of specialized computers called *routers*. Each *router’s* job is to know how to move *packets* along from their source to their destination. A *packet* will have moved through multiple *routers* during its journey.

When a *packet* moves from one *router* to the next, it’s called a *hop*. You can use the command line-tool `traceroute` to see the list of hops packets take between you and a host.

The *Internet Protocol* specifies how network *addresses* should be attached to the *packet’s* *headers,* a designated space in the *packet* containing its meta-data. The *Internet Protocol* also specifies how the *routers* should forward the *packets* based on the *address* in the *header*.

#### How do applications communiicate over the Internet?

Like many other complex engineering projects, the Internet is broken down into smaller independent components, which work together through well-defined interfaces. These components are called the *Internet Network Layers* and they consist of *Link Layer*, *Internet Layer*, *Transport Layer*, and *Application Layer*. These are called layers because they are built on top of each other; each layer uses the capabilities of the layers beneath it without worrying about its implementation details.

Internet applications work at the *Application Layer* and don’t need to worry about the details in the underlying layers. For example, an application connects to another application on the network via TCP using a construct called a [*socket*](http://pubs.opengroup.org/onlinepubs/009695399/basedefs/sys/socket.h.html), which abstracts away the gritty details of routing *packets* and re-assembling *packets* into *messages*.

> from [Lee](https://medium.com/@User3141592/how-does-the-internet-work-edc2e22e7eb8)

#### Summary

First, we need to link each computer on the network to a router.

Second, when a router is not enough, we connect the router to the router,and we can imagine that we will get infinite scale.

Third, we use modems to connect everyone's diffenrent networks.

Fourth, is to send information from our network to the place we want to reach.We need to connect our network to an Internet service provider([ISP](https://zh.wikipedia.org/wiki/%E4%BA%92%E8%81%94%E7%BD%91%E6%9C%8D%E5%8A%A1%E4%BE%9B%E5%BA%94%E5%95%86)).

Last, the Internet allows us to connect thousands of computers together.Among these computers, som computers(er call them web servers) can send some information that the browser can understand.The Internet is an infrastructure, and the network is a service built on this infrastructure.



### What is HTTP?

<strong>HTTP</strong> stands for <strong>H</strong>yper <strong>T</strong>ext <strong>T</strong>ransfer <strong>P</strong>rotocol

<strong>WWW</strong> is about communication between web <strong>clients</strong> and <strong>servers</strong>

Communication between client computers and web servers is done by sending <strong>HTTP Requests</strong> and receiving <strong>HTTP Responses</strong>.

### Browsers and how they work?

A browser is a software application used to locate, retrieve and display content on the World Wide Web, including Web pages, images, video and other files. As a client/server model, the browser is the client run on a computer that contacts the Web server and requests information. The Web server sends the information back to the Web browser which displays the results on the computer or other Internet-enabled device that supports a browser.

### DNS and how it works?

The Domain Name System (DNS) is the phonebook of the Internet. Humans access information online through domain names, like nytimes.com or espn.com. Web browsers interact through Internet Protocol (IP) addresses. DNS translates domain names to IP addresses so browsers can load Internet resources.

The process of DNS resolution involves converting a hostname into a computer-friendly IP address. An IP address is given to each device on the Internet, and that address is necessary to find the appropriate Internet device - like a street address is used to find a particular home.

When a user wants to load a webpage, a translation must occur between what a user types into their web browser and the machine-friendly address necessary to locate the example.com webpage.

In order to understand the process behind the DNS resolution, it’s important to learn about the different hardware components a DNS query must pass between. For the web browser, the DNS lookup occurs “ behind the scenes” and requires no interaction from the user’s computer apart from the initial request.

### What is Domain Name?

A domain name is your website name. A domain name is the address where Internet users can access your website. A domain name is used for finding and identifying computers on the Internet. Computers use IP addresses, which are a series of number. However, it is difficult for humans to remember strings of numbers. Because of this, domain names were developed and used to identify entities on the Internet rather than using IP addresses.

The domain name must be registered before you can use it.

### What is hosting?

Web hosting is a service that allows organizations and individuals to post a website or web page onto the Internet. A web host, or web hosting service provider, is a business that provides the technologies and services needed for the website or webpage to be viewed in the Internet. Websites are hosted, or stored, on special computers called servers. When Internet users want to view your website, all they need to do is type your website address or domain into their browser. Their computer will then connect to your server and your webpages will be delivered to them through the browser.