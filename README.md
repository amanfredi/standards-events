Standards & Guidelines For Defining Events
==========================================

### Inter-departmental communication via events

At Gilt we've agreed on open standards and tools (HTTP, JSON, DNS) for inter-departmental synchronous communication.

For asynchronous inter-departmental communication [Avro](http://avro.apache.org/docs/current/) has been chosen as the de facto
standard for event definition and transport.

### Avro IDL

[Avro IDL](http://avro.apache.org/docs/current/idl.html) is the
standard tool we choose for defining Avro schemas at Gilt.

The primary benefit of IDL is how the focus of the documents is the
schema itself which we think will lead to higher quality reviews over
time.

### Repository

Due to the importance of getting the inter-departmental communication
API right we encourage creating a separate repository with high
visibility and tight governance for defining your Avro schemas.

By convention the repository should be named: `events-<protocol>` where
`<protocol>` should be repaced by the name of the Avro protocol you are
defining.

We include major version numbers in the namespace. Note that all
changes to events sharing a major version number must by definition in
Avro be backwards compatible.

For example. if you create a repo named 'events-orders' we would
expect to see an Avro idl file containing:

    @namespace("com.gilt.orders.v1")
    protocol Orders {
      ...
    }

View all existing events repositories at
[GitHub](https://github.com/gilt?query=events)

### Contribution & Governance

We recommend thorough review of schema changes for each repository. The recommended repository structure at Gilt:

  1. Create a MAINTAINERS file in the root of the repository listing all of the people whose opinion we really need in reviewing changes to the schema. Each line in the maintainers file should follow the structure:
  
      &lt;github username&gt; (full name)
      
      The first line of the file should be the [Benevolent Dictator for Life](https://en.wikipedia.org/wiki/Benevolent_dictator_for_life). In the maintainers file, append "BDFL" to appropriate name.
      
      See [the MAINTAINERS file for this repo](https://github.com/gilt/events-standards/blob/master/MAINTAINERS) for an example.

  2. Create a team in github named "governance-protocol" with `write` access
to the repository (all others having `read`-only access).

  3. Create a "CONTRIBUTIONS.md" file in the rood of the repository that describes the policy by which contributions will be accepted. The standard Gilt policy is modeled after the docker hub project. Pls feel free to link directly to the [standard CONTRIBUTIONS.md policy](https://github.com/gilt/events-standards/blob/master/CONTRIBUTIONS.md) for your project.

### GFC Avro

GFC (or Gilt Foundation Classes) is a standard namespace for key libraries that we open source at Gilt. We have shared avro schemas in the [events-gfc-avro
repository](https://github.com/gilt/events-gfc-avro). You can pull in the
latest version of these schemas with the following command:

    bash
    curl -s -o target/gfc.avdl \
          "https://raw.githubusercontent.com/gilt/events-gfc-avro/master/events.avdl"

### Dates and timestamps

In general, for non primitive types, we are following the guidelines of the types documented at [apidoc](http://www.apidoc.me/doc/types).

Specific schemas for common types will be listed here as recommendations for teams to adopt.


## Contribution guidelines

See https://github.com/gilt/events-standards/blob/master/CONTRIBUTIONS.md
