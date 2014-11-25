Standards & Guidelines For Defining Events
==========================================

### Inter-departmental communication via events

At Gilt we've agreed on open standards and tools (HTTP, JSON, DNS) for inter-departmental synchronous communication.

For asynchronous inter-departmental communication [Avro](http://avro.apache.org/docs/current/) has been chosen as the de facto
standard for event definition and transport.

### Avro IDL

[Avro IDL](http://avro.apache.org/docs/current/idl.html), being the Avro
standard for authoring schemas, is the tool we choose for defining Avro
schemas at Gilt.

### Repository

Due to the importance of getting the inter-departmental communication API right we encourage creating a separate repository with high visibility and tight governance for defining your Avro schema.

By convention the repository should be named: `events-<protocol>` where
`<protocol>` should be repaced by the name of the event protocol you are
defining. E.g. events-orders, events-gfc-avro or events-mobile-tapstream.

### Contribution & Governance

To ensure thorough review of API changes we encourage tight governance of
changes to event definitions via clear ownership & contribution practices.

Clear ownership is generally defined by a MAINTAINERS file in the repository
listing the people whose opinion counts towards reviewing changes as well as
creating a team in github named `governance-<protocol>` with `write` access
to the repository (all others having `read`-only access).

A set of best practice contribution guidelines can be found in the
`CONTRIBUTIONS.md` that is part of this repository.

### gfc.avro

Pull in [GFC Avro](https://github.com/gilt/events-gfc-avro)

### Dates and timestamps

## Contribution guidelines
See https://github.com/gilt/events-standards/blob/master/CONTRIBUTIONS.md
