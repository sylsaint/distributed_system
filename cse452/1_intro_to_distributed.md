### prerequisite

### basics

1. A program: your code
2. A process: instance
3. A message: used to communicate between processes
4. A packet: piece of message
5. A protocol: description of message format and rules that two processes must follow in order to exchange messages
6. A network: infrastructure which links computers
7. A component: where process can run
8. A distributed system: is an application that executes a collection of protocols to coordinate the actions of multiple processes on a network, such that all components cooperate together to perform a single or small set of related tasks.

*Why distributed systems?*

1. open: each component can open to communicate with other components or leave them
2. scalable: with ability to handle change of users, resources and components

*requirements keep distributed system reliable*

1. fault-tolerant
2. highly-available
3. recoverable
4. consistent
5. scalable
6. predictable performance
7. secure


*view of [https://en.wikipedia.org/wiki/Ken\_Arnold](https://en.wikipedia.org/wiki/Ken_Arnold)*

Failure is the defining difference between distributed and local programming, so you have to design distributed systems with the expectation of failure. Imagine asking people, "If the probability of something happening is one in 10^13, how often would it happen?" Common sense would be to answer, "Never." That is an infinitely large number in human terms. But if you ask a physicist, she would say, "All the time. In a cubic foot of air, those things happen all the time."
When you design distributed systems, you have to say, "Failure happens all the time." So when you design, you design for failure. It is your number one concern. What does designing for failure mean? One classic problem is partial failure. If I send a message to you and then a network failure occurs, there are two possible outcomes. One is that the message got to you, and then the network broke, and I just didn't get the response. The other is the message never got to you because the network broke before it arrived.
So if I never receive a response, how do I know which of those two results happened? I cannot determine that without eventually finding you. The network has to be repaired or you have to come up, because maybe what happened was not a network failure but you died. How does this change how I design things? For one thing, it puts a multiplier on the value of simplicity. The more things I can do with you, the more things I have to think about recovering from.

conclusion: design towards failure.

*category of software bugs*

Software failures are a significant issue in distributed systems. Even with rigorous testing, software bugs account for a substantial fraction of unplanned downtime (estimated at 25-35%). Residual bugs in mature systems can be classified into two main categories:

1. Heisenbug: A bug that seems to disappear or alter its characteristics when it is observed or researched.
2. Bohrbug: A bug (named after the Bohr atom model) that, in contrast to a heisenbug, does not disappear or alter its characteristics when it is researched.

And Heisenbug seem to be prevalent in distributed systems than local systems. We can go deeper in to specific bugs in distributed systems:

1. Halting failures: A component simply stops, no way to detect this except timeout.
2. Fail-stop: A halting failure with notifying other components that it would stop.
3. Omission failures: fail to receive/send messages from/to other components due to lack of buffering space.
4. Network failures
5. Network partition failure: A network fragments into two or more disjoint sub-networks
6. Timing failures: time is not synchronized between computers
7. Byzantine failures: containing several types of failure including

