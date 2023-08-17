---
description: >-
  Use these patterns to give user’s control over how you manage their data.
  These patterns align with the GovStack Consent building block.
---

# Asking users for consent

<div data-full-width="true">

<figure><img src="../../.gitbook/assets/Asking for consent.png" alt=""><figcaption></figcaption></figure>

</div>

Related building block: [GovStack Consent building block](http://127.0.0.1:5000/o/pxmRWOPoaU8fUAbbcrus/s/MhCVws4MKdm6FWXf006q/).

## How it works

Consent covers all activities done for the same reason. If you use the data for more than one reason, get separate consent for each. For example, accessing data to check eligibility is separate to accessing data to make an application.

Use these patterns when you need to:

* To access a user’s data
* To store, manage or share a user’s data
* Allow users to manage the data you hold on them

## When not to use these patterns

You do not need to ask for consent when:

* the data is required for government to perform a specific task or function set out in law, you do not need to ask for consent. For example, terms and conditions — these are required so you do not need to ask for consent
* a person is simply informed of the processing of the data by the organisation as part of the service provided under contract or by an authority
* consent does not have to be obtained in a situation where the entity does not identify or cannot identify people with reasonable effort

## Consent page

This pattern allows users to accept or reject a request to access or share data for the use of a service. For example, asking to access data from social insurance records in order to check eligibility for another service.

User journey considerations:

* Consent should be grouped by purpose meaning you may need multiple consent pages&#x20;
* You may need to ask for consent at the start of a service or throughout the user journey
* you may need to offer users an opportunity to review and correct data using the [check your answers pattern](http://127.0.0.1:5000/o/pxmRWOPoaU8fUAbbcrus/s/zdXe8NbIMZIv5sydPBf6/).
* You should test your service with users to find the journey that works for them.

<div align="center" data-full-width="true">

<figure><img src="../../.gitbook/assets/Consent for a single data set.png" alt=""><figcaption><p>A wireframe of consent for a single data set</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Consent for a single data set mockups.png" alt=""><figcaption><p>A mockup of consent for a single data set</p></figcaption></figure>

</div>

<div data-full-width="true">

<figure><img src="../../.gitbook/assets/Consent for multiple data sets.png" alt=""><figcaption><p>A wireframe of consent multiple data sets</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Consent for multiple data set mockups.png" alt=""><figcaption><p>A mockup of consent for multiple  data sets</p></figcaption></figure>

</div>

### **Why we ask to share this data**

Explain what data you are requesting and the benefit to the user for sharing that data. For example, “Provide your location data so that we can tailor offers relevant to you”

### **About the data**

Be clear about:

* Why you need it and the benefit to the user
* How the data will be used and for how long

### **Confirm or reject**

If you are handlingg a simple data set, present the data you are collecting followed by a checkbox to explicitly confirm consent.

If you are handling multiple data sets allow the user to choose which data is shared.

## Implied consent

If you do not need to ask for consent but you are handling user data this should be specified in the privacy statement.

\[Add guidance on when that should be presented to the user]

## Handling data beyond the transaction

If the service will be accessing or sharing user data on an ongoing basis then you need to give users a method of managing consent. See point 6 [https://govstack-global.atlassian.net/wiki/spaces/GH/pages/183205908/Future+Considerations+Consent](https://govstack-global.atlassian.net/wiki/spaces/GH/pages/183205908/Future+Considerations+Consent).

## **Managing consent**

\[Give details for how to manage data if the user changes their mind.]

## Delegated consent

In cases where the person giving consent is doing so on behalf of someone else, as a guardian or carer.

\[This pattern is in the backlog]

## Additional details for information collection

When asking users information during a questions flow consider using progressive disclosure drop-downs or inline content to explain why you are asking for that information and how you will handle the data.

<figure><img src="../../.gitbook/assets/Details for information (1).png" alt=""><figcaption><p>A wireframe of an example progressive disclosure details pattern</p></figcaption></figure>

###
