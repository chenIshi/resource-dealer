# resource-dealer
A simple dealer to help students to share their public resources.

## Motivation

Recently I find out that most students follows a really primitive way to share their shared resources. 
For example, people have to register the usage of some music instruments on a physical paper or using 
communication software to notify other people (which interestingly matches the "acquire lock" action 
in real live). Some even crazier story involves waiting in line for the usage of piano (where everyone can 
have two hour of practicing, which means the waiting time can be terribly long).

Although these tricks do work, it always make me wonder if I can do something about it. As a result, I plan 
to design a simplified system to help students manages their shared resources. And most important of all, 
help me practice my design ability.

## Objective

1. Written in golang
This is not a must-have requirement. It is simply because I want to practice my golang skill after first learn 
in MIT 6.824.

```
It is possible to attach the final work from MIT 6.824 as a distributed database in this system. However, first I 
had mostly forgotten what I had done there one year ago; second I want to discover the valid options in the industry.
```

2. Minimum server burden
For now I think non-distributed database should be enough for some simple shared resource management. However, 
it would still be better to relieve the workload on server. That is because the server performance is usually the bottleneck of the whole system.

For current first-step plan, I want to reduce the state kept on server. For example, making the client responsible for 
memorizing the session key. 

3. High performance
The high performance here I want is not just a slogan. At first I don't even want to apply database as backend since 
applying database also introduce throughput limit. However, due to the need for fault tolerance, a database should still 
be necessary as backup in case the host machine go down.

As a result, I am currently seeking for nosql database. However, if there are some better choices with lower resource usage or higher performance I could change my mind.

4. Website interface
Although I do hate to deal with the messy front-end stuff, it should still be necessary for normal students to access this system. However, this means that the backend server might have to also served as a httpd/httpsd server. 
It should be better to decouple this two functionality. However, given that most students are poor, while the club 
mostly don't have that much extra fund for seperate servers, I planned to place this two in the same server. 

```
However, this still seem a little bit creepy to me, where there should be a firewall-like server in a formal design flow 
```
