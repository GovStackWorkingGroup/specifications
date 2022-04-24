# 8 Data Structures

### 8.1 Voucher Resource Model <a href="#docs-internal-guid-2e7883c1-7fff-2230-02ab-f41e68a34a31" id="docs-internal-guid-2e7883c1-7fff-2230-02ab-f41e68a34a31"></a>

The voucher resource model is shown below.

![](../../.gitbook/assets/image10.png)

### 8.1.1 Minimum Required Data

| **Data element**    | **Description**                                                   | **Type** | **Required** |
| ------------------- | ----------------------------------------------------------------- | -------- | ------------ |
| Vouchers ID         | Unique voucher identifier                                         | Int64    | yes          |
| Voucher\_Number     | Secret voucher number                                             | Varchar  | Yes          |
| Voucher\_serial\_no | Unique voucher identifier for external parties                    | Varchar  | Yes          |
| Currency            | Voucher currency                                                  | Varchar  | Yes          |
| Create\_date        | Date when the voucher was created                                 | Date     | Yes          |
| Activate\_date      | Date when the voucher was activated                               | Date     | Yes          |
| Expiry\_date        | Date when voucher will expire                                     | Date     | Yes          |
| Voucher\_group      | Voucher group                                                     | Varchar  | Yes          |
| Status              | Status of the voucher (e.g. ACTIVATED, SUSPENDED, CONSUMED, etc.) | Varchar  | Yes          |
| Value               | Value of the Voucher                                              | Double   | Yes          |

### 8.1.2 Voucher Groups

| **Data element**     | **Description**                 | **Type** | **Required** |
| -------------------- | ------------------------------- | -------- | ------------ |
| Vouchers ID          | Unique voucher group identifier | Int64    | Yes          |
| Voucher\_group       | Voucher group short code        | Varchar  | Yes          |
| Voucher\_group\_desc | Voucher description             | Varchar  | Yes          |

## 8.2 Incoming Government Payments Resource

![](<../../.gitbook/assets/image13 (1).png>)

## 8.3 Data Elements <a href="#docs-internal-guid-8d4f18ff-7fff-2f74-3bc3-2f4c2a3f0a1b" id="docs-internal-guid-8d4f18ff-7fff-2f74-3bc3-2f4c2a3f0a1b"></a>

### 8.3.1 API Name: Voucher APIs

| **Name**                | **Description**                                                     | **Type**          | **Required** | Standard | Notes  |
| ----------------------- | ------------------------------------------------------------------- | ----------------- | ------------ | -------- | ------ |
| voucher\_amount         | Denomination of the voucher required                                | Integer           | Y            |          | Input  |
| voucher\_currency       | The currency of the voucher                                         | String            | Y            | ISO 4217 | Input  |
| voucher\_group          | The group of the voucher                                            | String            | Y            |          | Input  |
| voucher\_number         | The voucher number (PIN). This is the secret number of the voucher. | Integer: 64-bit   | Y            |          | Output |
| voucher\_serial\_number | The voucher serial number.                                          | Integer: 64-bit   | Y            |          | Output |
| expiry\_date            | The expiry date of the voucher.                                     | String: date-time | Y            |          | Output |
| status                  | The status of the process: SUCCESSFUL or FAILED                     | String            | Y            |          | Output |
| Merchant\_group         | The group of the merchant is captured in the registry.              | String            | Y            |          | Input  |
| Gov\_Stack\_BB          | Calling GOV Stack Building Block                                    | String            | Y            |          | Input  |
| merchant\_bank\_details | Merchant / agent payment details                                    | String            | Y            |          | Input  |
| merchant\_name          | Merchant name                                                       | String            | Y            |          | Input  |
| Override                | Override                                                            | Boolean           | Y            |          | Input  |
| Result\_Status          | Result of the process                                               | String            | Y            |          | Output |

### 8.3.2 API Name: Bulk Payment &#x20;

| **Name**          | **Description**                              | **Type**        | **Required** | Standard    | Notes             |
| ----------------- | -------------------------------------------- | --------------- | ------------ | ----------- | ----------------- |
| Program\_name     | Program that beneficiary is participating in | String          | Y            |             | Input             |
| Program\_category | Program Category                             | Integer         | Y            | <p><br></p> | Input             |
| Beneficiary\_name | First and last ...                           | String          | Y            |             | Input             |
| Identity\_token   | Internal to government systems               | Integer: 64-bit | Y            |             | Input             |
| Identity\_info    | Other identity information as required       | String?         | Y            |             | Input             |
| Set recurring     | type of payment                              | Boolean         | Y            |             | Input             |
| Start Date        | start date                                   | Date            | <p><br></p>  | <p><br></p> | Input             |
| End Date          | end date                                     | Date            | <p><br></p>  | <p><br></p> | Input             |
| Batch\_ID         | <p><br></p>                                  | Integer         | <p><br></p>  | <p><br></p> | Output            |
| Batch\_note       | <p><br></p>                                  | String          | <p><br></p>  | <p><br></p> | <p>Output<br></p> |

### 8.3.3 API Name: Incoming Government Payment

| **Name**                                                            | **Description**                                                                                                                                                                                                                                   | **Type**                           | **Required** | Standard    | Notes       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------- | ------------ | ----------- | ----------- |
| Program\_name                                                       | Program that beneficiary is participating in                                                                                                                                                                                                      | String                             | Y            |             | <p><br></p> |
| Program\_category                                                   | Program Category                                                                                                                                                                                                                                  | Integer                            | Y            | <p><br></p> | <p><br></p> |
| transactionReference                                                | Unique reference for the transaction. This is returned in the response by the API provider.                                                                                                                                                       | string                             | y            | <p><br></p> | <p><br></p> |
| <p>requestingOrganisation</p><p>TransactionReference</p><p><br></p> | A reference provided by the requesting organisation that is to be associated with the transaction                                                                                                                                                 | string                             | y            | <p><br></p> | <p><br></p> |
| creditParty                                                         | <p>A series of key/value pairs that enable the credit party to be identified. Keys include MSISDN and Wallet Identifier. creditParty must be supplied if debitParty is omitted.</p><p>If debitParty is supplied, then creditParty is optional</p> | array                              | <p><br></p>  | <p><br></p> | <p><br></p> |
| debitParty                                                          | A collection of key/value pairs that enable the debit party to be identified. Keys include MSISDN and Wallet Identifier.                                                                                                                          | array                              | <p><br></p>  | <p><br></p> | <p><br></p> |
| transactionStatus                                                   | Indicates the status of the transaction as stored by the API provider.                                                                                                                                                                            | string                             | <p><br></p>  | <p><br></p> | <p><br></p> |
| amount                                                              | string                                                                                                                                                                                                                                            | The transaction amount.            | y            | <p><br></p> | <p><br></p> |
| currency                                                            | string                                                                                                                                                                                                                                            | Currency of the transaction amount | y            | ISO 4217    | <p><br></p> |

## 8.4 Account Identifiers

The Account Identifier enumeration lists all possible means to identify a target account. Identifiers can be combined if necessary, to provide a unique identifier for the target beneficiary account.

| **Code**        | **Short Description**           | **Type** | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| --------------- | ------------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| accountcategory | Account Category                | string   | Can be used to identify the sources of funds category where there are multiple accounts (wallets) held against an account holder.                                                                                                                                                                                                                                                                                                                                                                     |
| bankaccountno   | Bank Account Number             | string   | Financial institution account number that is typically known by the account holder.                                                                                                                                                                                                                                                                                                                                                                                                                   |
| accountrank     | Account Rank                    | string   | Is used to identify the rank of the source of funds where there are multiple accounts (wallets) held against an account holder.                                                                                                                                                                                                                                                                                                                                                                       |
| identityalias   | Identity Alias                  | string   | An alias for the identity, e.g. short code for an agent till.                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| iban            | IBAN                            | string   | Internationally agreed system of identifying bank accounts across national borders to facilitate the communication and processing of cross border transactions. Can contain up to 34 alphanumeric characters.                                                                                                                                                                                                                                                                                         |
| accountid       | Account Holder Identity         | string   | Identifier for the account holder.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| msisdn          | MSISDN                          | string   | <p>Must contain between 6 and 15 consecutive digits</p><p>First character can contain a ‘+’ or digit</p><p>Can contain spaces.</p>                                                                                                                                                                                                                                                                                                                                                                    |
| swiftbic        | SWIFTBIC                        | string   | A bank identifier code (BIC) is a unique identifier for a specific financial institution. A BIC is composed of a 4-character bank code, a 2-character country code, a 2-character location code and an optional 3-character branch code. BICs are used by financial institutions for letters of credit, payments and securities transactions and other business messages between banks. Please refer to [ISO 9362](http://www.iso.org/iso/catalogue\_detail?csnumber=60390)  for further information. |
| sortcode        | Bank Sort Code                  | string   | Sort code to identify the financial institution holding the account.                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| organisationid  | Organisation Account Identifier | string   | Used to identify the organisation for which a payment is to be made.                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| username        | Username                        | string   | Used to identify target account via an associated username.                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| walletid        | Wallet Identifier               | string   | A means to identify a mobile money wallet, particularly where multiple wallets can be held against an MSISDN. typically used in conjunction with MSISDN or identity alias to identify a particular wallet.                                                                                                                                                                                                                                                                                            |
| linkref         | Link Reference                  | string   | A means to uniquely identify an account via an account to account link. E.g. wallet account link to bank account.                                                                                                                                                                                                                                                                                                                                                                                     |
| consumerno      | Consumer Number                 | String   | Identifies the consumer associated with the account.                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| serviceprovider | Service Provider                | String   | Provides a reference for a Service Provider.                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| storeid         | Store ID                        | String   | Identifies the transacting store / retail outlet.                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| bankname        | Bank Name                       | String   | Name of the bank.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |