# 3 Terminology

## 3.1 Keyword Usage

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [BCP 14](https://tools.ietf.org/html/bcp14) [RFC2119](https://tools.ietf.org/html/rfc2119) [RFC8174](https://tools.ietf.org/html/rfc8174) when, and only when, they appear in all capitals, as shown here.

## **3.2 Building Block**

1. From this document: “Building blocks are software modules that can be deployed and combined in a standardized manner. Each building block is capable of working independently, but they can be combined to do much more.” Read more: [above. (And please read this!)](description.md#2.3-building-blocks)
2. An application which provides re-usable interfaces:
   1. An **admin-only form builder** which facilitates building user interfaces (e.g., select questions to be displayed in a maternal-and-child-health registration process)
   2. **User interfaces** (i.e., forms) which can be used in lieu of individual end-user apps building their own forms (e.g. I’m building a _new_ maternal and child health application; I’d like to use a registration screenflow that’s been pre-built in the registration building block as part of a larger, _composed_ application.)
   3. A **public API** which exposes the critical **back-end services** performed by this BB (adding a mom to a database; checking for a mom’s enrollment status in a program) to be used (as a microservice) by existing or new applications with legacy/bespoke needs (e.g., i’ve already got a maternal and child health app that the CHWs are using, and I want to send a webhook to the registration BB after a CHW clicks “submit” on our custom form.)

## 3.3 Registration

Any approval/license/certificate issued by a public entity as a result of a request/declaration made by a user of the public service. The result of a “registration” is usually a number and/or a document (called certificate, license, permit, authorization, registration, clearance, approval, etc.)

## 3.4 Authentication <a href="#_vuk04bv7cgij" id="_vuk04bv7cgij"></a>

This is the technical process of establishing that the credentials (i.e. username, password, biometric etc.) provided by a party (user, system, other) is valid and that the party can be granted basic access to system resources with default access rights. Note that authorization also needs to be applied for a party to access protected resources.

## 3.5 Authorization

This is the technical process of establishing whether or not an authenticated party has rights to access a given protected resource. Access rights can typically be granted or revoked administratively on a read-only and/or read-write and/or execute basis through an administrative provisioning process. Permissions or rights defined for a party typically manifest in an access token that is granted at the time of authentication for the party. Hence the processes of authentication and authorization are intrinsically related.

## 3.6 Workflow[ ](https://docs.google.com/document/d/1TIQ756eWauQLNeSWUqfm5dpDz\_wJsesfZgXBiWXLx9w/edit#heading=h.8dexf2kkoftd)Terminology

See more comprehensive descriptions of the workflow terminoloy in the [Workflow and Business Process Automation Building Block specification](https://govstack.gitbook.io/specification/building-blocks/workflow).

* (Workflow) Activity - a single step in a workflow process.
* (Workflow) Process - a workflow process contains one or many activities.
* (Workflow) Instance - an instance of execution for a workflow process.
