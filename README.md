# Tweets: a dev assignment

This repo aims at solving a development [assignment](./assignment.md) using Spring Boot + Webflux. Leveraging reactive streams allows for potential scaling of the app far beyond the requirements of the assignment.

## Solution

Although the assignment only processes a very limited amount of data, the solution aims at providing a baseline for scalabilty. Using reactive streams allows for arbitrary large data sets to be processed. In this case, the amount of followers and applicable tweets for a user can easily reach in the millions resulting in standard relational patterns line `Lists` and `Sets` to be insufficient. Another option would have been to use paging, but reactive stream have a range of properties making it a much better choice.
   
Some notes:
- The solution implements `application/stream+json` REST endpoints, by which one can query the data.
- The assignment asks for a certain console output, this is present in the output of a [integration test](test/java/io/springtide/tweets/TweetsApplicationTests.java) since the actual rendering of the data in a specific format can be argued to be client specific.

## Getting Started

Check of the repo and run the tests to see the required console output:
~~~~

./mvnw test 
(in Linux)

~~~~
~~~~
mvnw.bat test
(in Windows)

~~~~

## TODO

Some more work is required/desired:
- Replace the custom repositories with a proper JPA reactive datastore, like MongoDB.
