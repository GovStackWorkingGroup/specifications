# 5 Cross-Cutting Requirements

Building blocks are responsible for meeting all cross-cutting requirements or specifying why specific requirements do not apply. Govstack compliance and certification processes will validate these requirements.

## 5.1 APIs MUST Return a Response within 60 Seconds

## 5.2 MUST follow TM Forum Specification REST API Design Guidelines Part 1 <a href="#_wyofs1ddrlgk" id="_wyofs1ddrlgk"></a>

See: [https://drive.google.com/file/d/1lpl1IzLGzvbXALW4jqDxLAKqfwuJyeXy/view?usp=sharing](https://drive.google.com/file/d/1lpl1IzLGzvbXALW4jqDxLAKqfwuJyeXy/view?usp=sharing)

## 5.3 SHOULD follow TM Forum Specification REST API Design Guidelines Parts 2-7 <a href="#_19suuzwtdje" id="_19suuzwtdje"></a>

See [https://drive.google.com/drive/u/2/folders/1eS20wt\_PP7CoJEOvzagYDTTMCfmv3y6l](https://drive.google.com/drive/u/2/folders/1eS20wt\_PP7CoJEOvzagYDTTMCfmv3y6l)

## 5.4 EOL MUST be at Least 5 Years <a href="#_fo8til974qj2" id="_fo8til974qj2"></a>

Nothing SHALL be used in a block that has an EOL of less than 5 years.

## 5.5 MUST Only Use TIOBE Top 25 Languages

See [https://www.tiobe.com/tiobe-index/](https://www.tiobe.com/tiobe-index/)

## 5.6 MUST Use API-only Based Decoupling <a href="#_8vqx9ylj3l5" id="_8vqx9ylj3l5"></a>

## 5.7 SHOULD Follow the Amazon API Mandate

See [https://api-university.com/blog/the-api-mandate/](https://api-university.com/blog/the-api-mandate/)

1. All teams will henceforth expose their data and functionality through service interfaces.
2. Teams must communicate with each other through these interfaces.
3. There will be no other form of interprocess communication allowed: no direct linking, no direct reads of another team’s data store, no shared-memory model, no back-doors whatsoever. The only communication allowed is via service interface calls over the network.
4. It doesn’t matter what technology is used \[ed: internally]. HTTP, Corba, Pubsub, custom protocols — doesn’t matter.
5. All service interfaces, without exception, must be designed from the ground up to be externalizable. That is to say, the team must plan and design to be able to expose the interface to developers in the outside world. No exceptions.
6. Anyone who doesn’t do this will be fired. Is this enforcable?

## 5.8 GET and PUT APIs MUST be Idempotent

GET and PUT APIs (as well as HEAD, OPTIONS, and TRACE) must be idempotent, returning the same value if called multiple times. POST and DELETE APIs will not be idempotent as they change the underlying data. Reference [https://restfulapi.net/idempotent-rest-apis/](https://restfulapi.net/idempotent-rest-apis/) for more information.

## 5.9 Stateless APIs SHOULD be Used Wherever Possible to Enhance Scalability

## 5.10 Regular Security and Code Quality Audits MUST be Run

Thse should be run across the code base and dependencies, e.g. [https://www.sonarqube.org/](https://www.sonarqube.org) and/or [https://snyk.io/](https://snyk.io) .

## 5.11 MUST Include Integration Test Coverage

## 5.12 MUST Include Support for a Log Sink

## 5.13 Data Models MUST Include Version Numbers

## 5.14 APIs MUST be Versioned

As shown here: e.g. /api/v1 and /api/v2

## 5.15 API Calls MUST Include Transaction/Trace/Correlation IDs

## 5.16 MUST Use Semantic Versioning

See [https://semver.org/](https://semver.org/)

## 5.18 MUST Include Clearly-Defined Key Rotation Policies

Some blocks may require the use of security keys. Those that do must have clearly defined key rotation policies to enhance security

## 5.19 Documentation MUST be Generated from Code and/or Checked in Alongside Source Code

## 5.20 MUST Not Use Shared Database/Filesystem/Memory

interconnection uses APIs only

## 5.21 Databases MUST Not Include Business Logic

This means no triggers/stored procedures shall be used.

## 5.22 MUST Enforce Transport Security

HTTPS with TLS 1.3 and insecure cyphers disabled.

## 5.23 MUST Only Use Unicode for Text

## 5.24 MUST Use ISO8601/UTC for Timestamps

## 5.25 MUST Follow REST Design Principles

MUST not include PII/session keys in URLs - use POST or other methods for this

MUST support caching/retries

* Resource identification in requests Individual resources are identified in requests, for example using [URIs ](https://en.wikipedia.org/wiki/Uniform\_resource\_identifier)in RESTful Web services. The resources themselves are conceptually separate from the representations that are returned to the client. For example, the server could send data from its database as [HTML](https://en.wikipedia.org/wiki/HTML), [XML ](https://en.wikipedia.org/wiki/XML)or as [JSON](https://en.wikipedia.org/wiki/JSON)—none of which are the server's internal representation.
* Resource manipulation through representations When a client holds a representation of a resource, including any [metadata ](https://en.wikipedia.org/wiki/Metadata)attached, it has enough information to modify or delete the resource's state.
* Self-descriptive messages Each message includes enough information to describe how to process the message. For example, which parser to invoke can be specified by a [media type](https://en.wikipedia.org/wiki/Media\_type).

See [https://en.wikipedia.org/wiki/Representational\_state\_transfer](https://en.wikipedia.org/wiki/Representational\_state\_transfer) for more.

## 5.26 MUST be Asynchronous First

* When entities change, they publish events, allowing loosely-coupled solutions to be assembled without changing existing APIs.\
  Supports occasional connectivity/low bandwidth

## 5.27 MUST Support Both SAAS and Do-It-Yourself

* Many new governments prefer cloud-based deployments
* SAAS is preferred to make it easy for companies to provide new services
* Anyone should be able to test/deploy building blocks by themselves

## 5.28 MUST be Autonomous

Each block must be capable of running independently.

## 5.29 MUST be Open-source Only with No Vendor Lock-in

Each block must be composed of open-source software unless there are no alternatives.

## 5.30 MUST be Cloud Native

* Each block MUST be ready to be deployed as independent Docker images, with complete source code and build instructions committed to GitHub.
* A block may be composed with Kubernetes or docker compose. All build files must be included alongside the source code.

## 5.31 MUST Use Standardized Configuration

* Configuration MUST only happen through environment variables or secrets
* Allows visual construction of blocks, perhaps with domain modeling tools

## 5.32 MUST Use Standardized Data Formats for Interchange

JSON is used for data models/services. See [https://www.json.org/json-en.html](https://www.json.org/json-en.html)

## 5.33 MUST Use Existing Standards for Data Interchange, Where Available

If an existing standard is available, it should be used, e.g. DICOM/Hl7/FHIR for healthcare. TMForum has a large library of standardized APIs and data models that can be used.

## 5.34 I/O Sanitization MUST be Used

* See an example [https://json-schema.org/ ](https://json-schema.org)for JSON data.
* Follows Postel’s law: be liberal in what you consume but strict in what you emit

## 5.35 MUST Include Machine-Readable API descriptions

## 5.36 MUST Provide a Compliance Test Kit

Each block’s service APIs are defined using a standardized machine-readable language. External APIs are described using the OpenAPI 3.0 specification for APIs: [https://swagger.io/docs/specification/about/](https://swagger.io/docs/specification/about/)

## 5.37 MAY Provide a Compliance Test Mock/Example Implementation

A building block MAY provide a mock testing implementation of API functionality to show example endpoints and data payloads. See [https://github.com/GovStackWorkingGroup/bb-template/tree/main/examples](https://github.com/GovStackWorkingGroup/bb-template/tree/main/examples) for additional information.

## 5.37 MUST Use Web Hooks for Callbacks

## 5.38 MUST be Internationalizable

## 5.39 SHOULD Follow Best Practices for Public Code

See [https://standard.publiccode.net/](https://standard.publiccode.net) and practices outlined here:

* [Code in the Open](https://standard.publiccode.net/criteria/code-in-the-open.html)
* [Bundle Policy and Source Code](https://standard.publiccode.net/criteria/bundle-policy-and-code.html)
* [Create Reusable and Portable Code](https://standard.publiccode.net/criteria/reusable-and-portable-codebases.html)
* [Welcome Contributions](https://standard.publiccode.net/criteria/open-to-contributions.html)
* [Maintain Version Control](https://standard.publiccode.net/criteria/version-control-and-history.html)
* [Require Review of Contributions](https://standard.publiccode.net/criteria/require-review.html)
* [Document Your Objectives](https://standard.publiccode.net/criteria/document-objectives.html)
* [Document your code](https://standard.publiccode.net/criteria/documenting.html)
* [Use plain English](https://standard.publiccode.net/criteria/understandable-english-first.html)
* [Use open standards](https://standard.publiccode.net/criteria/open-standards.html)
* [Use continuous integration](https://standard.publiccode.net/criteria/continuous-integration.html)
* [Publish with an open license](https://standard.publiccode.net/criteria/open-licenses.html)
* [Use a coherent style](https://standard.publiccode.net/criteria/style.html)
* [Pay attention to codebase maturity](https://standard.publiccode.net/criteria/advertise-maturity.html)

## 5.40 MUST Follow Strict Requirements Around NTP/RTC Synchronization

## 5.41 If an API Response will Take Longer than 5 Seconds, you SHOULD Return a Ticket with a Suggested Callback Time that is Resolved by Polling

## 5.42 MUST be deployable as a container

* Each building block MUST be ready to be deployed as independent container images. Source code and build instructions SHOULD be committed to a public code repository where possible.
* A block may be composed with Kubernetes or docker compose. All build files must be included alongside the source code.

## 5.43 SHOULD Include Kubernetes or Ansible Scripts

In addition to Docker Compose for more efficient and scalable deployments. This will make individual components of the building block independently scalable and make building blocks less monolithic and more efficient,

## 5.44 SHOULD Comply with GDPR Principles

Include the right to be forgotten account deletion), privacy requirements to protect the rights of individuals, etc. Note that these requirements may vary by region.

## 5.45 MUST Implement Existing Standards Where Possible

Building blocks and building block solutions MUST leverage existing standards, especially those listed in the [Standards section](6-standards.md) below.
