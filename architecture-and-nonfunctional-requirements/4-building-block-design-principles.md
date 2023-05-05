# 4 Building Block Design Principles

While the following principles are relevant to many technology deployments, when leveraging the GovStack approach it is important to keep these principles in mind during all phases of design, development, and deployment.

## 4.1 Citizen-Centric

Design of systems should be rooted in the needs of the citizens/users of these platforms. A Citizen-centric technology will include the following attributes:

* User-centered design
* Right to be forgotten: everything must be deletable

The best tools evolve from empathizing, understanding and designing for the needs of end-users. Accordingly, we’ve identified a series of use cases and user journeys here: [GovStack Use Cases](https://govstack.gitbook.io/product-use-cases)

Each use case is composed of a collection of modules, or building blocks. As you can see, a relatively small set of these building blocks can be readily applied to a wide variety of applications in low-resource settings.

## 4.2 Open <a href="#_hj7wrge29nf5" id="_hj7wrge29nf5"></a>

Where possible, GovStack advocates for the use of open technology, which can reduce cost and help avoid vendor lock-in. Open technology can be defined as:

* Based on open standards
* Based on Digital Development Principles, see [https://digitalprinciples.org/](https://digitalprinciples.org) and [https://digitalinvestmentprinciples.org](https://digitalinvestmentprinciples.org)[/](https://digitalinvestmentprinciples.org)
* Built on open-source software where possible
* Supports open development, see [https://standard.publiccode.net/](https://standard.publiccode.net)
* Cloud native where possible (Docker/Docker Compose/OCI containers)

## 4.3 Sustainable <a href="#_5fv1ildee3ef" id="_5fv1ildee3ef"></a>

Any Building Blocks should be developed in a manner which is sustainable and ensures that the technology will continue to be updated and maintained. Some core considerations for sustainability are:

* Stewardship is critical, see [https://publiccode.net/codebase-stewardship/](https://publiccode.net/codebase-stewardship/)
* Continuous funding for maintenance, development and evolution, which results in lower long-term costs
* Uses microservices-based architecture instead of monolithic.
  * This increases interoperability, development and deployment speed and reliability.
  * From Wikipedia: a variant of the[ ](https://en.wikipedia.org/wiki/Service-oriented\_architecture)[service-oriented architecture](https://en.wikipedia.org/wiki/Service-oriented\_architecture) (SOA) structural style – arranges an application as a collection of[ ](https://en.wikipedia.org/wiki/Loose\_coupling)[loosely coupled](https://en.wikipedia.org/wiki/Loose\_coupling) services. In a microservices architecture, services are fine-grained and the protocols are lightweight.

## 4.4 Secure <a href="#_1tvbgx5xc0is" id="_1tvbgx5xc0is"></a>

With any technology deployment, security is paramount. Detailed security requirements are defined in the [GovStack Security Requirements](https://govstack.gitbook.io/specification/security-requirements). Beyond those standards, Building Blocks should have the following attributes:

* Building Blocks are audited and certified before being made available
* Development processes and standards enforce quality and security
* Different certification levels reflect level of standards-compliance
* Regular security scanning and auditing
* Public ratings and reviews
* Comprehensive logging and exception handling

## 4.5 Accessible <a href="#_64y5ys9r1wf3" id="_64y5ys9r1wf3"></a>

It is vitally important that technology solutions be usable by _all_. Some characteristics of accessible design include:

* Meets users where they are: web, mobile, SMS and/or voice. UI supports accessibility technologies, e.g. screen readers.
* SSO allows for signing in once for multiple services
* Shared ownership of code
* Deployment and development processes and standards are open to contributors
* Community-driven development tools for documentation and support
* Blueprints, templates and documentation

## 4.6 Flexible <a href="#_ul5nalat80jf" id="_ul5nalat80jf"></a>

GovStack is rooted in the concept that Building Blocks should be re-usable and configurable, such that they can support multiple use cases with minimal effort:

* Building Blocks can be reused in multiple contexts
* Each Building Block is autonomous
* Building Blocks are interoperable, adhering to shared standards
* Building Blocks should be easy to set up
* Standardized configuration and communications protocols should be used to connecting Building Blocks
* Building Blocks can be provided as a service (ICT opportunity)

## 4.7 Robust <a href="#_jgyljayvwagf" id="_jgyljayvwagf"></a>

Deployments of Building Blocks should follow these principles:

* Any client-facing functionality should operate in low-resource environments:
  * Occasional power
  * Low bandwidth
  * Low-reliability connectivity
* Easily scalable for high availability and reliability
* API-only based decoupling
* Asynchronous communications pattern decoupled through rooms is ideal
* Eventual consistency for data
