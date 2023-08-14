# 3 GovStack Architecture

The following diagram provides an example of a GovStack implementation

<figure><img src="../.gitbook/assets/GovStack Overall Architecture.png" alt=""><figcaption></figcaption></figure>

This digram shows an example of what a GovStack implementation may look like in practice. Several concepts that are important to GovStack are shown in this diagram:

* A GovStack implementation may consist of multiple ‘applications’, each serving a distinct purpose. The value that GovStack provides is that these applications do not have to be developed from scratch, but rather leverage core functionalities that are provided by various Building Blocks. And these Building Blocks may be used in multiple applications.
* Applications may access outside services through the Information Mediator. Access to these services are configured within the Information Mediator per organization. One application may have permission to access data provided by a particular ministry that another application may not access.
* A GovStack application can be used by different types of users. The roles and permissions for various user groups must be managed by the application itself (using [authorization services described here](https://govstack-global.atlassian.net/wiki/spaces/GH/pages/239370263))
* Building Blocks may be based on existing applications or Digital Public Goods (DPGs). These DPGs may have an API that conforms with the GovStack API specification for that Building Block. If not, an [adaptor](https://govstack-global.atlassian.net/wiki/spaces/GH/pages/215318576) can be used to map the existing API to the GovStack API
* The Application frontend and backend may use any mechanism to communicate (REST, GraphQL, etc). However, all GovStack API calls should be done using standard REST protocols.



## GovStack Components

