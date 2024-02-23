
# 2023-2024 RSP4J-Advanced Windowing

Optional #project of the [Streaming Data Analytics](http://emanueledellavalle.org/teaching/streaming-data-analytics-2022-23/) course provided by [Politecnico di Milano](https://www11.ceda.polimi.it/schedaincarico/schedaincarico/controller/scheda_pubblica/SchedaPublic.do?&evn_default=evento&c_classe=811164&polij_device_category=DESKTOP&__pj0=0&__pj1=1b82965d3c68857e2087d3f3b98a9e40)

### Prerequisites

- Java Programming
	- Java 8+
	- MVN
- Functional Programming (basics)
## Description 

Traditional Data Stream Management Systems (DSMS) break down data streams into sections using windows based on time intervals or specific amounts of data. These windows are set in place and don't change, even if the data stream itself changes over time, like getting faster or slower, or the kind of data being streamed changes.

However, since data streams can change in how fast data comes in or what the data is about, sticking to one way of breaking down the streams doesn't always work well. This is why we need a new, more flexible way to divide up data streams.

Grossniklaus et al.  introduced a new method called _frames_. Unlike the old way, frames divide streams based on what's in the data itself. We've developed a theory and a way to use frames, and we'll show how frames can be really useful for different kinds of applications.

## Project Goal

This project aims at implementing window frames within the Library RSP4J.
RSP4J is a library to build RDF Stream Processing (RSP) Engines according with the reference model RSP-QL.

RDF is a graph data model for the Web. RDF streams are infinite sequences of RDF timestamped RDF data. The library is inspired by the OWL API, and attempt to uniform the access to existing RDF-based DSMS. 
## Requirements

![[frames.png]]

- Implement the different types of frames indicated in the paper Grossniklaus et al.  
	- Threshold Frames
	- Delta Frames
	- Boundary Frames
	- Aggregate Frames
- Implement the additional Session Windows 
- Design Test Cases for the Frames 
- Design and Implement an extended syntax fro specifying frames in RSP-QL
- Create the documentation for the code and guide examples
## Material

### RSP4J

In this [repository](https://github.com/streamreasoning/rsp4j), you will find several information about RSP4J, including

- API, which contains the interfaces and abstractions required to develop your RSP engine.
- Yasper, which is an reference implementation that aims at showing the API usage by providing org.streamreasoning.rsp4j.yasper.examples.
- examples to understand the general functioning of RSP4J

#### Window Operators in RSP4J

RSP4J combines the logic of CQL and SECRET. It identified operators according to three families (see figure below)

![[cql.png]]

The internals of window operator follow the logic of SECRET. They are operationalised according to four functions: tick, scope, content, and report. The operations needs to be redefined for incorporating the Frame semantics. Example of existing implementation for time-based sliding windows are linked below.

- [Example from C-SPARQL](https://github.com/streamreasoning/rsp4j/wiki/C-SPARQL-SLIDING-WINDOW-OPERATOR)
- [Example from CQELS](https://github.com/streamreasoning/rsp4j/wiki/CQELS-SLIDING-WINDOW-OPERATOR)
### Datasets

The project should work with two datasets, 

- [DEBS Challenge 2017](https://ckan.project-hobbit.eu/dataset/debs-grand-challenge-2017)
- and a synthetic dataset to be created for the test cases.


## References

- [Frames](https://kops.uni-konstanz.de/server/api/core/bitstreams/55c23a7a-242f-4530-bee9-b2597fb5b76a/content)
- [RSP4J](https://openreview.net/pdf?id=IbXJmD1i2WA)
