# 2 Description

This document is intended to be used as a reference for the security requirements for GovStack by vendors proposing solutions for all building blocks as well as vendors proposing solutions for this security building block.

Security requirements address all cross-cutting security issues and concerns for the whole GovStack digital platform including every layer, every building block and all applications. Although other building blocks address “some” security aspects such as “Identity building block” (addressing the foundational identity aspects and document workflows etc.) the resultant solutions delivered by all building-blocks (including the “Identity building block”) MUST comply with the standards and requirements set by this security requirements document. This document covers security requirements of two types:

* **Build-time Security**: These are considerations for embedding security during development of building blocks and applications.
* **Deployment time Security**: These are considerations for enforcing security measures in deployed systems during run-time.

These may consist of cross cutting functionalities that can be utilized for various building blocks and specific requirements for the **Security Building Block itself, to** provide secure internet access for user interaction with applications and building blocks in Govstack.

The security requirements are based on the [NIST CyberSecurity Framework](https://www.nist.gov/cyberframework/getting-started) and defined herein through review of GovStack use cases and best practices for securing and hardening government infrastructure. It MUST also be noted that the security building block defines the core requirements to implement policy based API security and management across the internal building blocks as well as external applications and 3rd party services consumption. This is based on the architectural assumption that all inter-building block communication/integration with external applications and users MUST be through REST APIs.



## 2.1 Security Building Block Modules

Though these security requirements are cross-cutting, this document also provides guidance on specific modules that should be provided by a 'security building block' in most technology deployments. These modules include support for:

* API Gateway functionality which will manage incoming requests&#x20;
* Identity and Access Management and/or Role-Based Access Control.&#x20;

These modules are described in Section 6 of this document.
