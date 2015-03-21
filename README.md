Introduction
============
Covering the first three lectures given by Jiri Pinkas.
They are [excellent](https://www.youtube.com/watch?v=dEnVDoi9iok)
This project contains the first three parts, and that's why this project is named
springtut13.

So, the scope is simply setting up your IDE and making your first Spring Web MVC
app run through the Spring dispatcher servlet, a controller and a JSP page.

Issues
======
This is a rather harsh opinion, but I have to say that doing Java development
is somehow not pleasant. Somehow things are rather too complicated. Here are
my reflections as I tried to make this example work.

### 1. Why is Logging This Hard?
Application logging is a basic and given. But given the way things happened in
Java (historically), the tension between the JDK team and the Apache Projects grew and 
unfortunately, Java app developers suffered. With something as mundane as logging,
we have Java Util Logging (JUL), Apache Commons Logging, Apache4J, Logback, SL4J and
perhaps more. 

In order to understand what a framework is doing (and how it achieves its magic(!?)),
one should look at logging and not the wad of documentation. But looking to find the
location of the log configuration file was painful. I learned that Spring uses
log4j via the Apache Commons Logging (which is a facade) and although its configuration
is easier, it still makes me do a lot of Google searches. Then there is an idea of
Loggers and Appenders and Layout in log4j. So, here's a question: How do you make
Spring framework spit all the log records to stdout i.e. console of your IDE?

This project's log4j.properties tries to answer that. Once I configured it that way,
I saw that Spring framework methods spit out the information at the session scope,
application scope and request scope. What happens at application load time, at every
request, what Spring does to route web requests etc. become clear.
