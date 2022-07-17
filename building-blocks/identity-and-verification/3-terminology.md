# 3 Terminology

**Authentication**

* The process or action of verifying the identity of a user or process. For the purpose of this project, authentication has been replaced with the term ‘verification’ to allow for a clearer definition and for demarcation with other building blocks.

**Biographic data (or Demographic data)**

* Set of text attributes representing the identity given at birth
* Common attributes: Name, firstname, birthdate, birthplace, parents biographic data

**Biometric data**

* Set of physical attributes which can be used to identify a person
* Most common ones are fingerprints, face and iris
* More can be used like voice, behavioral, veins, etc.
* Those data can be used for different reasons:
  * Establishing uniqueness of a person
  * Verifying a person identity
  * Identifying an unknown person
  * Claiming an identity
  * Verifying presence or liveness;
  * Deduplication

**Civil Registry**

* A civil registry or CRVS (Civil Registry and Vital System) is a system recording life events (birth, death, mariage, divorces, adoptions, name changes, …) It is used to keep track of life events of individuals and to produce statistics for policy making.

**Claim**

(Following is a general description of claims. For the purpose of this document only the first claim description is relevant since claims for foundational identity only refer to the question ‘who are you’ and not ‘what are you’)

* Can be pertaining to identity - I am X
* Can be pertaining to entitlement or eligibility - X is allowed to vote
* Can be pertaining to membership - X is an employee of Y corp
* Can be pertaining to ownership - X owns Z car
* Can be pertaining to role - X is a doctor
* Can be pertaining to any other identity association - X is an organ donor, X studied subject Y at Institution Z
* Can protect persons privacy by disclosing state of attributes without disclosing the attribute itself (ie “is older than 18” don’t need to share the age)
* Can be pertaining to 3rd party claim i.e I claim that something is answerable at a 3rd party verification place

**Credential**

Taken from WB ID4D, Practitioners Guide, Glossary, [https://id4d.worldbank.org/guide/glossary](https://id4d.worldbank.org/guide/glossary); adapted from ID4D Technology Landscape and Public-Private Cooperation reports.

* A document, object, or data structure that vouches for the identity of a person through some method of trust and authentication. Common types of identity credentials include—but are not limited to—ID cards, certificates, numbers, passwords, or SIM cards. A biometric identifier can also be used as a credential once it has been registered with the identity provider.

**Credential management**

* Is a document lifecycle management regardless of its form. An identity credential can appear in both physical (ID card, passport, driver’s license) and electronic form (eID);
* Includes issuance, maintenance, suspension, termination of suspension, revocation and expiration;
* There should be no difference between physical and electronic documents with the exception of audit trail kept during usage of the electronic document (eID).

**Digital Identity**

(Adjusted from ITU, Digital Identity Roadmap Guide, 2018, [http://handle.itu.int/11.1002/pub/81215cb9-en](http://handle.itu.int/11.1002/pub/81215cb9-en))

* Digital identity is the unique representation of a subject engaged in an online transaction. A digital identity is always unique in the context of a digital service, but does not necessarily need to uniquely identify the subject in all contexts. In other words, accessing a digital service may not mean that the subject’s real-life identity is known.
* The digital identity allows an entity (citizen, business, administration) to be distinguished from any other.
* A set of digitally captured and stored attributes and/or credentials that satisfactorily within context identify someone or something.
* Is a ‘representation of an entity in the form of one or more attributes that allow the entity or entities to be sufficiently distinguished within context’. Building on this definition, we might state that a digital identity is the digital representation of an entity detailed enough to make the individual distinguishable within a digital context.

**Digital Identifier**

* Digital identity fundamentally requires digital identifiers—strings or tokens that are unique within a given scope (globally or locally within a specific domain, community, directory, application, etc.). Identifiers are the key used by the parties to an identification relationship to agree on the entity being represented. Identifiers may be classified as omnidirectional and unidirectional.\[19] Omnidirectional identifiers are intended to be public and easily discoverable, while unidirectional identifiers are intended to be private and used only in the context of a specific identity relationship.
* Identifiers may also be classified as resolvable or non-resolvable. Resolvable identifiers, such as a domain name or e-mail address, may be dereferenced into the entity they represent, or some current state data providing relevant attributes of that entity. Non-resolvable identifiers, such as a person's real-world name, or a subject or topic name, can be compared for equivalence but are not otherwise machine-understandable.
* There are many different schemes and formats for digital identifiers. The most widely used is Uniform Resource Identifier (URI) and its internationalized version Internationalized Resource Identifier (IRI)—the standard for identifiers on the World Wide Web. OpenID and Light-weight Identity (LID) are two web authentication protocols that use standard HTTP URIs (often called URLs), for example. A Uniform Resource Name (URN) is a persistent, location-independent identifier assigned within the defined namespace.
* Source: https://en.wikipedia.org/wiki/Digital\_identity

**Electronic Identity (eID)**

An electronic identity:

* is a means for the user to prove electronically that they are who they say they are and thus gain access to services;
* is presented in electronic environment;
  * can appear in a form of certificate, username or email address or phone number;
* preferably is associated with an electronic identity hardware token;
* ideally has a hard link back to digital identity.

**Electronic Identity Token**

A secure electronic identity token

* is a hardware device to be used during electronic transactions in order to provide for electronic identity verification process;
* provides for additional level of assurance;
* stores a set of private keys with corresponding public keys;
* carries at least functions of electronic authentication and digital signature creation.

**Electronic Transaction**

* Is between two or more parties
  * The parties can be anonymous (privacy is protected if only attributes / details associated with claims are shared). This may involve a coordination hub that removes metadata that would allow the identity provider to have knowledge of which service was being accessed.
  * The transaction could be indifferent to the identity of the parties involved, since it is atomic or trust and repudiation is not a concern
  * Trust is needed on the identity of the parties for legal recourse, reversal, or non-repudiation
  * Parties are entities - Persons, Businesses or Things
  * If the party is a Thing, it is then deemed acting on behalf of a Person or a Business
* A transaction is a multi-step interaction and each step could involve flow of data or instructions
* At a step level there is a need for trust on the parties and the data
* At a transaction level there is a need for trust on the parties, the data and factors such as eligibility and permissions
* Privacy and security principles of need to know, selective disclosure, access control, information security against snooping are needed

**Foundational Identity System (fID System) (also referred to as legal identification system)**

(Adjusted from WB ID4D, Practitioners Guide, Glossary, [https://id4d.worldbank.org/guide/glossary](https://id4d.worldbank.org/guide/glossary))

An identification system primarily created to manage identity information for the general population and provide credentials that serve as proof of identity for a wide variety of public and private sector transactions and services. Common types of foundational identification (ID) solutions include civil registries, universal resident or national ID systems, and population registers.

\
Typical capacities include::

* Provide recognition before the law and proof of legal identity.
* The name and nature of legal identification systems varies under national law, but typically includes civil registration systems, national identification systems, population registries, and other foundational identification systems.
* Maintains a registry of natural persons and provides issuance and lifecycle management of foundational identities.
* Those persons are people needing to interact with a country: citizens, diaspora, foreign residents, foreign workers, refugees, etc.
* Has an identity issuance and management process that takes care of accuracy of information in order to act as a reliable root of trust.
* Offers identity assurance in the form of identity verification in the digital realm.
* Digital identity and electronic identity serve as foundational level attributes.

**Functional Identity**

(Adapted from PRINCIPLES ON IDENTIFICATION, February 2021. Retrieved from: [https://documents1.worldbank.org/curated/en/213581486378184357/pdf/Principles-on-Identification-for-Sustainable-Development-Toward-the-Digital-Age.pdf](https://documents1.worldbank.org/curated/en/213581486378184357/pdf/Principles-on-Identification-for-Sustainable-Development-Toward-the-Digital-Age.pdf))

* Is linked to systems which have a specific function with specific business rules: ie education, healthcare, justice, .. are functional domains which could establish and use functional Identities.
* Functional identification systems provide official proof of identity and authorization for particular purposes or sectors. This typically includes identification systems that provide voter identification, ration cards, social security numbers, health cards, tax numbers, and more; in some cases these credentials may also be recognized as proof of identity for other purposes or sectors.
* Historically functional identities are created in the absence of / as complements to foundational identities. In the presence of proper foundational eID, there is no further need for a separate functional eID.
* Is often associated with a credential that provides entitlements - a functional health identity card both provides identity services of a kind and entitles the holder to access health care services

**Functional Identity System**

A functional identity system

* Maintains a registry of credentials.
* Associates the identity of a person with the entitlement that the functional credential offers.
* Optionally offers uniqueness based on the credential type.
* Optionally offers identity assurance based on the credential type.
* Optionally digital based on the credential type.

**Identity Credential**

* An identity document in a physical or digital form that an identity credential holder may present to authenticate his identity in a physical or electronic interaction;
* Data, or the physical object upon which the data may reside, that an identity credential holder may present to authenticate his identity in an electronic or online transaction.

**Identity Registry**

* An identity registry contains individuals identity information, it can be related to group or sub-groups (ie for a functional system, a region, a company)

**Identity verification**

* Offers mechanisms for verifying a person’s identity locally or by hitting a service offering the verification capabilities
* Local verification involves trusting the source of the information by (for example) using digital signatures rather than having to go back to the root source of truth (and hence creating a privacy invasive audit record of the check)
* Identity verification services might be available in synchronous and asynchronous modes and might have real time or non real time responses
* Online identity verification uses a single or multi-factor mechanism. Identity verification involves an identifier and the factors. The identifier may be the UIN or an alias that is associated with the UIN in reference to the eID term described above..
* A foundational identity system can offer verification services in a centralized or multi-provider (federated/ distributed) model.
* In a federated model identity verification has to come from different sources based on the credential used. This means that there is a need for discovery, registration, resolution and routing of verification requests to the appropriate verification service. This needs a web of trust model to be defined. Such a model will also be repeatable for cross border usage where it will be dealing with a federation of foundational identity systems.

**IDV BB**

* Stands for Identity and Verification Building Block
* Building block specified in current documentation
* In charge to create, manage life cycle, audit mechanisms, and verify identities

**Population registry**

* A population registry is a database/system which includes records of the entire population of a country covering citizens but also foreigners staying in the country and also the national diaspora.

**UIN**

* Stands for Unique Identity Number, this number uniquely identifies a person in the Foundational ID system. UIN are an optional approach and not necessary.
