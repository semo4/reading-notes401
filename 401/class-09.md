# WRRC and Java

# The HTTP Request Lifecycle
![images](https://img.webnots.com/2013/06/HTTP-Request-and-Response-Over-Web.png)

- it contain multi steps before send the request

1. Step 1: Local Processing
2. Step 2: Resolve an IP
3. Step 3: Establish a TCP Connection
4. Step 4: Send an HTTP Request
5. Step 5: Tearing Down and Cleaning Up


# Simple HTTP Request in
![images](https://i.ytimg.com/vi/0OrmKCB0UrQ/hqdefault.jpg)

## HttpUrlConnection
- The HttpUrlConnection class allows us to perform basic HTTP requests without the use of any additional libraries. All the classes that we need are part of the java.net package.

## Creating a Request
- We can create an HttpUrlConnection instance using the openConnection() method of the URL class. Note that this method only creates a connection object but doesn't establish the connection yet.

## Adding Request Parameters
- If we want to add parameters to a request, we have to set the doOutput property to true, then write a String of the form param1=value¶m2=value to the OutputStream of the HttpUrlConnection instance

## Setting Request Headers
- by using the setRequestProperty()

## Configuring Timeouts
- HttpUrlConnection class allows setting the connect and read timeouts. These values define the interval of time to wait for the connection to the server to be established or data to be available for reading.