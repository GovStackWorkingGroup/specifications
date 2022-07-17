# 8 APIs and Services

The following **external** APIs must be implemented by the Identity & Verification building blocks:

* **Enrollment Services** : Registration of Identity and applications services
* **ID Usage (Identity Verification)** : Identity verification Services
* **Credential Services** : Issuance and management of identity credentials
* **Notifications**: Subscription and notifications of event

The following **internal** APIs could be implemented by the Identity & Verification building blocks:

* **Data Access**: Access and management of identity data
* **Biometrics**: Interoperability API for ABIS systems, Interoperability with devices, operations on biometric data (Segmentation, Quality Check, Templatization, Format Conversion, Matching, Liveness Check, Compression, Attribute Annotation)
* **Population Registry services** : Access and management of persons in Population registry
* **UIN Management**: Generation of Unique Identity Numbers
* **Data Portability**: The ability to migrate from one implementation of Identity and Verification Building Block to another. The identity data and associated transaction history should be portable.

## 8.1 External APIs

### 8.1.1 Enrollment API

The Enrollment APIs are a set of OpenAPI specifications exposed by the Identity and Verification Building Block (IBB) ‘Enrollment Server’ service to any enrollment client.

The Enrollment APIs are based on the following principles:

* When enrollment is done in one step, the CreateEnrollment can contain all the data and an additional flag (finalize) to indicate all data was collected.
* During the process, enrollment structure can be updated. Only the data that changed needs to be transferred. Data not included is left unchanged on the server. In the following example, the biographic data is not changed.
* Images can be passed by value or reference.
* Existing standards are used whenever possible, for instance preferred image format for biometric data is **ISO-19794**. The underlying data should be of open mime types that offer good compression without loss of data (for example JPEG2000 for images).

Any implementation of the Identity and Verification building block must support these Enrollment APIs documented at this site: [link to GovStack API portal](https://github.com/GovStackWorkingGroup/BuildingBlockAPI/issues/5).

The API definition file can be found here:

1. [Technical descriptio](https://osia.readthedocs.io/en/latest/05%20-%20interfaces.html#enrollment-services)
2. [Yaml file\
   ](https://osia.readthedocs.io/en/latest/annexes/technical/enrollment.html)

### 8.1.2 Identity Verification API

The Identity verification API is an OpenAPI specification exposed by the Identity and Verification Building Block (IDV BB) ‘Identity Verification’ service to relying parties. The scope of the API is to allow the verification of an Identity credential and a set of identity attributes. Verification is strictly matching all provided identity attributes to compute the global Boolean matching result.

This service brings:

* the ability to use multiple identity verification factors
* security features:
  * verification and response can be bound to one transaction,
  * verification factor data can be signed and encrypted,
  * requests can be checked for integrity.
* privacy features:
  * the consent on usage of its data of the citizen/user can be provided,
  * selective disclosure of attributes based on authorization given for the use case to the relying party.
  * Supports tokenization of the response by including a pseudonymous customer reference (Token ID).

Any implementation of the Identity and Verification Building Block must support the identity verification APIs documented at this site:[ GovStack API portal](https://github.com/GovStackWorkingGroup/BuildingBlockAPI/issues/5)

The API definition file can be found here:

* [Technical description](https://osia.readthedocs.io/en/latest/05%20-%20interfaces.html#id-usage)
* [Yaml file](https://osia.readthedocs.io/en/latest/annexes/technical/idusage.html)

### 8.2 Building Block API Requirements

This section lists the GovStack Identity & Verification building block high level and generic requirements to be followed by the candidate implementations of Building Blocks.

Those requirements are there to guide the building block implementers in making their components match the needs of the GovStacks. We aim here to be specific enough in the requirements to allow a seamless integration of the candidate building block in the GovStack and at same time to keep latitude for the diversity of needs of countries, including for the resources constrained environments.

For each of them it is indicated if the requirement is Mandatory (M), Recommend (R) or Specific (S)

* To be recognized by GovStack, each building block will have to implement at minimum ‘Mandatory’ requirements.
* A 1 to 5 stars score will be established for the building block according to the ratio of ‘Recommended’ requirements implemented.
* ‘Specific’ requirements are generally required as mandatory by part of countries
  * They open the building block to diversity of needs, context and legacy in countries and are important for allowing the building block to match needs in some countries or regions.
  * Those requirements must be carefully considered by the Building Block providers (ie biometrics uniqueness, unique identifiers, ID cards with chip are mandatory in some regions and are not used in others)
  * In a further step this specification could attempt to define specific groups corresponding to countries having common constraints and needs, bringing to specific set of requirements (S1, S2, S3, ..)

Requirements have been grouped in domains for facilitating their use and evaluation.

### 8.2.1 Enrollment Services API Requirements

| **Name**                                           | **Name/Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                 | **M/R/S** |
| -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| Gov Stack recommended Open Standard Enrollment API | IDV BB must offer an API to Enroll persons following a Gov Stack recommended Open Standard API                                                                                                                                                                                                                                                                                                                                                                       | M         |
| One step Enrollment                                | IDV BB must offer capacity to perform an enrollment in one step                                                                                                                                                                                                                                                                                                                                                                                                      | M         |
| Multiple steps Enrollment                          | IDV BB must offer capacity to perform an enrollment in multiple steps (ie pre-enrollment and enrollment)                                                                                                                                                                                                                                                                                                                                                             | R         |
| Enrollment management                              | <p>IDV BB must offer capacity to search, retrieve and update and enrollment made (if it has not been committed yet)</p><p><br></p>                                                                                                                                                                                                                                                                                                                                   | S         |
| Enrollment integrity                               | <p>IDV BB must allow to control integrity and origin of an enrollment request by implementing enrollment meta-data about the context and actors of the enrollment, such as signature of data to ensure integrity. To ensure the integrity of the enrollment process, the BB must be able to implement technical controls so that only approved enrollment services can engage with the enrollment service. Cryptographic trust should be implemented.</p><p><br></p> | M         |
| Enrollment data encryption                         | IDV BB must support receiving encrypted data to ensure privacy protection and prevent data theft.                                                                                                                                                                                                                                                                                                                                                                    | M         |
| Offline Enrollment                                 | IDV BB must offer capacity to perform an enrollment offline which means not expecting interactions in between registration client and server during the enrollment process, data being uploaded as a whole packet                                                                                                                                                                                                                                                    | S         |
| <p>Enrollment traceability</p><p>identifiers</p>   | IDV BB must keep track of the enrollment request identifiers within its internal management in order to facilitate traceability and troubleshooting                                                                                                                                                                                                                                                                                                                  | R         |

### 8.2.2 Verification Services API Requirements

| **Name**                                                      | **Name/Description**                                                                                                                                                                                                                                                                                                                                                                                                            | **M/R/S** |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| Gov Stack recommended Open Standard Identity Verification API | IDV BB must offer an API to verify Identities following a Gov Stack recommended Open Standard API                                                                                                                                                                                                                                                                                                                               | M         |
| Verify Identity (Authenticate)                                | IDV BB must offer an API to Verify Identity of an individual based on one of its known identifiers and or more of his attributes.                                                                                                                                                                                                                                                                                               | M         |
| <p>Identity Attributes</p><p>sharing</p>                      | IDV BB must offer an API to retrieve personal attributes of an individual from one of its identifiers. To be noted that this service will be subject to preliminary access granted by the system and by the individual (informed consent). Authorized access control should be part of API as opposed to external configuration alone. This ensures that relying parties are verified by the API before sharing sensitive data. | M         |
| Identification of an individual                               | IDV BB must offer an API to identify an unknown individual, which means retrieve an identity identifier from a set of personal attributes sent. This service is normally to be used for security/law enforcement purposes and must be limited to registries of wanted people. For privacy and security reasons, this feature should only be considered where clear and accountable security/law enforcement rules are in place. | S         |
| Claim a characteristic                                        | IDV BB must offer an API to verify one characteristic of an individual without having to disclose actually the recorded related attributes. Typical request response is Yes or No (sample use case: age verification, is person older than 18 > Yes to No)                                                                                                                                                                      | R         |
| Identity Verification capabilities                            | IDV BB must offer Identity Verification services based on capabilities listed in present document (TBD developed more, include the different capabilities, all optionals) following a Gov Stack recommended ORen Standard API                                                                                                                                                                                                   | S         |

### 8.2.3 Credential Management Services API Requirements

This section introduces the requirements regarding the Credential Management Services API which will allow BB users to request issuance, manage, share and get status of ID Credentials.

| **Name**                                                      | **Name/Description**                                                                                                                                                                                                                                                                                                                                                                                                                                        | **M/R/S** |
| ------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| Gov Stack recommended Open Standard Credential Management API | IDV BB must offer an API Standard to request issuance, get status and manage Identity Credentials, following a Gov Stack recommended Open Standard API                                                                                                                                                                                                                                                                                                      | M         |
| Credential Life Cycle Management                              | IDV BB must offer an API to manage the full life cycle of credentials related to an identity in an issuing system. The related credential must keep a strong and verifiable link with the individual identity and with the issuer.                                                                                                                                                                                                                          | M         |
| Digital Credential                                            | IDV BB API must manage Digital Credentials                                                                                                                                                                                                                                                                                                                                                                                                                  | R         |
| Physical Digital                                              | IDV BB API must manage Physical Credentials                                                                                                                                                                                                                                                                                                                                                                                                                 | S         |
| Credential Issuance                                           | IDV BB must offer an API allowing to request an identity credential issuance to a 3rd party credential management system.                                                                                                                                                                                                                                                                                                                                   | M         |
| Data for Credential issuance                                  | IDV BB must offer APIs to either push data for credential issuance in an issuance request or to be requested by the issuing system.                                                                                                                                                                                                                                                                                                                         | M         |
| Credential Renewal                                            | IDV BB must offer an API allowing to issue a similar credential to the one already issued before based on the credential ID number.                                                                                                                                                                                                                                                                                                                         | S         |
| Credential Revocation                                         | <p>IDV BB must offer an API allowing to revoke an issued ID credential.</p><p>This will be used, for example, when a document is damaged, stolen or definitely lost.</p>                                                                                                                                                                                                                                                                                    | M         |
| Credential Temporary Suspension                               | <p>IDV BB must offer an API allowing to temporarily suspend then un-suspend an issued ID credential.</p><p>This will be used to disable an ID credential which has been lost, it’s holder suspending it the time to search for it. After retrieval the document should be unsuspended and usable again. If not retrieved after some time, the document should be revoked.</p><p>An API must be also available to check suspension status of a document.</p> | S         |
| Credential status request                                     | <p>IDV BB must offer an API to request status of ID credentials.</p><p>Status being related to their production, their delivery or their activation status.</p>                                                                                                                                                                                                                                                                                             | R         |
| Credential Search                                             | IDV BB can offer an API to search for ID credentials using some of its attributes. The output must be restricted to being a document number which can facilitate an access request only. No information can be shared directly.                                                                                                                                                                                                                             | S         |
| Credential Retrieval                                          | <p>IDV BB must offer an API to retrieve a new copy of an ID credential already issued in case the current document has expired.</p><p>The copy may be received through electronic way if being digital or delivered physically in case of a physical ID document.</p>                                                                                                                                                                                       | S         |
| Credential Download                                           | IDV BB must offer an API to download a newly generated digital ID credential                                                                                                                                                                                                                                                                                                                                                                                | S         |
| Credential Sharing                                            | IDV BB must offer an API to share to a 3rd party a Digital ID Credential.                                                                                                                                                                                                                                                                                                                                                                                   | S         |

### 8.2.4 Notification Services API Requirements

| **Name**                                             | **Name/Description**                                                                                                                                  | **M/R/S** |
| ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| Gov Stack recommended Open Standard Notification API | IDV BB must offer an API for notifying change on identity to subscribed external Building Blocks, following a Gov Stack recommended Open Standard API | R         |

### 8.2.5 Security and Access Control Requirements

| **Name**           | **Name/Description**                                                                                                                                                                               | **M/R/S** |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| Unauthorized users | MIDV BB must prevent any user unauthorized system or user to get access to data                                                                                                                    | M         |
| Registered users   | IDV BB must offer identity verification services only to registered system or users                                                                                                                | R         |
| Granted access     | IDV BB must offer capacity to grant access to specific verification services for specific or all individuals that are data subjects and hence owners of that data..                                | S         |
| Individual consent | IDV BB must offer identity verification services only with preliminary informed consent on personal data usage of the concerned individual                                                         | R         |
| Data Security      | IDV BB must respect principles of data security by design in order to maximize protection against hackers: data encryption, data isolation, data separation, data anonymization, data minimization | R         |
| System Security    | IDV BB systems must implement security best practices in order to ensure the Identities it manages can be trusted.                                                                                 | M         |

### 8.2.6 Privacy Protection Requirements

| **Name**                        | **Name/Description**                                                                                                                                                                                                                                                                          | **M/R/S** |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| Sharing unnecessary information | IDV BB must not disclose any personal unnecessary information as part of its services API, and when possible prefer Yes/No answer rather than sharing attributes. All Sensitive Personal Information / Personally Identifiable Information must not be written to logs / reporting databases. | R         |

#### 8.2.7 Identity Management Requirements

| **Name**                          | **Name/Description**                                                                                                                                                                                                                                                              | **M/R/S** |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| Enrollment of Identity            | IDV BB must allow to enroll an identity in one or several steps following a Gov Stack compliant Open Standard API                                                                                                                                                                 | M         |
| Update of Identity attribute      | IDV BB must off APIs to update attributes of identities and to attach a legal evidence of that identity change approval (often delivered by justice)                                                                                                                              | M         |
| Request for Identity Credential   | IDV BB must allow to trigger issuance of an Identity credential                                                                                                                                                                                                                   | R         |
| Revoke Identity Credential        | IDV BB must allow to disable an Identity credential in case it has been lost or stolen. This can apply to physical or digital credentials.                                                                                                                                        | R         |
| Get Status of Identity credential | IDV BB must offer a set of services for checking status of an Identity credential for use of its owner or for a side system. Objectives being mainly to know if it has been issued or not, if has been disabled (lost/stolen), if its genuine or has been modified by a fraudster | S         |

### 8.2.8 Identifiers Management Requirements

| **Name**                             | **Name/Description**                                                                                                                                       | **M/R/S** |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| At least one identifier per identity | IDV BB must assign at least identifier and possibly several identifiers to each identity allowing to use it/them when requesting services on that identity | M         |

### 8.2.9 Identity Uniqueness Requirements

| **Name**        | **Name/Description**                                                                                                                                                   | **M/R/S** |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| Unique identity | An identity must be unique as part of the IDV BB, this unicity can be established based on identity attributes such like biometrics when available or biographic data. | R         |

### 8.2.10 Auditability Requirements

| **Name**          | **Name/Description**                                                                                                        | **M/R/S**           |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------- |
| Auditable history | A history of change for any identity must be retrievable and auditable by authorized users to investigate suspicious cases. | <p>R</p><p><br></p> |

\*O/R/M: Optional/Recommendation/Mandatory
