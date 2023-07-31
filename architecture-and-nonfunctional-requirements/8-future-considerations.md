# 8 UX Switching and Handover

In many case, control over the User Interface may need to be passed from an application to another Building Block. For example, if a user is doing a biometric or multi-factor authentication, the ID Building Block can present the UX to the user for that process. If a user is sending or receiving a payment, the UX can be handed off to the Payment Building Block for the user to enter account information for the payment.&#x20;

Given that context, there are 4 potential ways in which this UX switching can be accomplished:

**1. OpenID Connect based Single Sign-On (SSO)**

A Single Sign On (SSO) system can be used, which allows an authentication token to be passed from the application to another Building Block. An authorization server is used to handle the initial user login and the access token received from the auth server can be passed to other Building Blocks and used to authorize access to the Building Block functionality.

**2. IFRAME based Secure Proxy Authentication**

A Building Block may provide a component that may be embedded as an iFrame within the application. Event handlers may be used to configure the flow of any information from the main application to the embedded frame.

**3. Token-based, decentralized Authentication**

In this method, a user authenticates in the application and a token is issued when the user starts a transaction. When the user clicks a relevant button on the screen of the application, it calls a UI of the Building Block at a predefined URL endpoint and passes the token along with any other information necessary. The same token is also passed to a secure backend API of the Building Block through the Information Mediator by the calling application backend.

**4. Hybrid Model**

This is a combination of openID Connect and Token based connect models and hence has advantages of both user and application authentication. This method requires more overhead, but ensures security on both the front-end and back-end. The application passes a token to the called Building Block through the Information Mediator, ensuring a valid registered application is sending the request. In addition, the called Building Block can authenticates a valid user with the authorization service.



Any of these mechanisms may be used, depending on the implementation. In general GovStack recommends option 1 or option 4.

The various approaches and recommendations, along with technical specifications for UX switching are outlined in detail in this document: [GovStack UX Switching](https://govstack-global.atlassian.net/wiki/spaces/GH/pages/270139400/UX+Switching)&#x20;
