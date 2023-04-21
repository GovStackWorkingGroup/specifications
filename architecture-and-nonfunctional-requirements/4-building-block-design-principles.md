# 4 Building Block Design Principles

## 4.1 Citizen-Centric

* Right to be forgotten: everything must be deletable
* User-centered design

The best tools evolve from empathizing, understanding and designing for the needs of end-users. Accordingly, we’ve identified a series of use cases and user journeys here: [GovStack Use Cases](https://govstack.gitbook.io/product-use-cases)

Each use case is composed of a collection of modules, or building blocks. As you can see, a relatively small set of these building blocks can be readily applied to a wide variety of applications in low-resource settings.

## 4.2 Open <a href="#_hj7wrge29nf5" id="_hj7wrge29nf5"></a>

* Based on open standards
* Based on Digital Development Principles, see [https://digitalprinciples.org/](https://digitalprinciples.org) and [https://digitalinvestmentprinciples.org](https://digitalinvestmentprinciples.org)[/](https://digitalinvestmentprinciples.org)
* Built on open-source software (where possible)
* Supports open development, see [https://standard.publiccode.net/](https://standard.publiccode.net)
* No vendor lock-in
* Cloud native (Docker/Docker Compose/OCI containers)
* Code is openly developed and available to anyone, via Github or Gitlab

## 4.3 Sustainable <a href="#_5fv1ildee3ef" id="_5fv1ildee3ef"></a>

* Stewardship is critical, see [https://publiccode.net/codebase-stewardship/](https://publiccode.net/codebase-stewardship/)
* Continuous funding for maintenance, development and evolution, which results in lower long-term costs
* Uses microservices-based architecture instead of monolithic.
  * This increases interoperability, development and deployment speed and reliability.
  * From Wikipedia: a variant of the[ ](https://en.wikipedia.org/wiki/Service-oriented\_architecture)[service-oriented architecture](https://en.wikipedia.org/wiki/Service-oriented\_architecture) (SOA) structural style – arranges an application as a collection of[ ](https://en.wikipedia.org/wiki/Loose\_coupling)[loosely coupled](https://en.wikipedia.org/wiki/Loose\_coupling) services. In a microservices architecture, services are fine-grained and the protocols are lightweight.

## 4.4 Secure <a href="#_1tvbgx5xc0is" id="_1tvbgx5xc0is"></a>

* Blocks are audited and certified before being made available
* Development processes and standards enforce quality and security
* Different certification levels reflect level of standards-compliance
* Regular security scanning and auditing
* Public ratings and reviews
* Comprehensive logging and exception handling

## 4.5 Accessible <a href="#_64y5ys9r1wf3" id="_64y5ys9r1wf3"></a>

* Meets users where they are: web, mobile, SMS and/or voice. UI supports accessibility technologies, e.g. screen readers.
* SSO allows for signing in once for multiple services
* Shared ownership of code
* Deployment and development processes and standards are open to contributors
* Community-driven development tools for documentation and support
* Blueprints, templates and documentation

## 4.6 Flexible <a href="#_ul5nalat80jf" id="_ul5nalat80jf"></a>

* Blocks can be reused in multiple contexts
* Each block is autonomous
  * Blocks are interoperable
  * Easy to set up
* Standardized configuration and communications protocols connecting blocks
* Blocks can be provided as a service (ICT opportunity)

## 4.7 Robust <a href="#_jgyljayvwagf" id="_jgyljayvwagf"></a>

* Any client-facing functionality should operate in low-resource environments:
  * Occasional power
  * Low bandwidth
  * Low-reliability connectivity
* Easily scalable for high availability and reliability
* API-only based decoupling
* Asynchronous communications pattern decoupled through rooms is ideal
* Eventual consistency for data
