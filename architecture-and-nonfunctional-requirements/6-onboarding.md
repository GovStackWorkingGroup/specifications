# 6 Onboarding Products

It is vital that GovStack be able to connect to existing applications. Likewise, existing applications should be able to connect to and utilize GovStack resources as they see fit. This must be done without compromising the easy and secure interoperability provided by the GovStack system.

This section describes a phased approach that existing platforms may use to integrate into a GovStack implementation. These phases are as follows:

* Adaptors
* API Gateways
* Native GovStack implementation

This can be accomplished with Adapters that connect existing applications for use by GovStack and API Gateways that provide secure access to GovStack services for citizens and other applications, including existing applications.

### 6.1 Adapters

Adapters connect GovStack building blocks to existing applications. There are many possible flavors of adapter, e.g. HL7 2.5, HL7 3.0, FHIR, SAP SOAP, SQL and many others. Each flavor can be quickly configured to give GovStack access to existing resources.

An adapter is used to translate an existing API that is provided by the application into a format that is consistent with the API definitions that are defined in the Building Block specifications. Adapters are responsible for data and protocol translation, authentication, and filtering and aggregation logic. They publish an OpenAPI specification so they can be used by any building block.

Here we can see two adapters, one for patient records and another for a tax registry:

![(github repo / image - link)](../.gitbook/assets/j2.png)

In this example, a registry adapter configured to map HL7 2.5 data connects an existing application’s patient record registry to a GovStack implementation. Another registry adapter providing SAP SOAP mapping connects an existing applications tax registry to GovStack. Both adapters provide services that are available for use by other building blocks.

If an existing application sends events, they should be exposed as web hooks in the adapter’s OpenAPI specification like other APIs. This allows any GovStack building block to be notified when the event occurs.

### 6.2 API Gateways

API gateways connect citizens and existing applications to GovStack Building Blocks. The API gateways map outbound API calls from the application into API calls that will be used and understood by the GovStack Building Blocks. Here, a public API gateway provides GovStack resources to citizens, while a private API gateway provides GovStack resources to existing applications:

![(github repo / image - link)](<../.gitbook/assets/image4 (4).png>)

In this example, a hospital information management system can use the Citizen ID/Authorization Building Block to authenticate a patient’s foundational ID. Likewise, citizens access government services via external mobile or web applications calling through a shared public API gateway.

Any number of API gateways can be added to expose various GovStack services to users or external applications, each of which have different security requirements on the information mediator and public internet/API Gateway sides.

### 6.3 Native GovStack Implementation

The highest level of integration involves existing products implementing APIs that can be directly consumed by other GovStack Building Blocks. The following diagram shows a complete GovStack deployment with API gateways for citizen access via web or mobile and for existing applications to be able to call GovStack APIs on demand. The workflow building block is used as an adapter, exposing existing applications as GovStack resources via OpenAPI:

![(open in https://app.diagrams.net/)](<../.gitbook/assets/image6 (2).png>)

Here, citizens and existing applications are provided API access for requests into GovStack via a common API Gateway, while the workflow Building Block adapter provides outgoing API access to existing applications from GovStack Building Blocks.
