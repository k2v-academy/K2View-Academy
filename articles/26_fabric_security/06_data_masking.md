# Fabric Data Masking

Data Privacy laws require the ability to mask data by hiding the original values with modified content. 
Fabric provides a field-level API to protect data classified as Personal Identifiable Information, sensitive personal data, or commercially sensitive data.

To ensure that the data is still valid for your data lifecycle management, the data will look real and appear consistent.

This capability can be used to conduct tests, implement data transformations, or serve anonymized data to external third parties via web services or queue messages.


## Masking Flow

 The masking of sensitive data can be done either by the [LUI sync](/articles/14_sync_LU_instance/01_sync_LUI_overview.md) using the [LU Table Population Broadway Flow](/articles/07_table_population/14_table_population_based_Broadway.md) (which masks the data before it is saved into Fabric), or by using a Broadway flow to mask the LUI data before it is loaded to the target.

The following diagram describes the masking process of a sensitive data using **LUI sync**:

![masking flow](images/masking_flow.png)



The following diagram describes the masking process of sensitive data **before loading the data to the target**:

![masking flow](images/masking_flow_load_to_target.png)



### Broadway Masking Actors

The masking process is executed by Broadway masking actors. Broadway provides a variety of masking actors that can be used to mask sensitive fields like SSN, credit card numbers, email addresses, zip code or sequences, before they are loaded into a target Database or even into Fabric. 

The masking actor uses the Fabric hashing utility to hash the original value, generates a masked value for the masked field, and saves the mapping of the hashed value and the masked value to the cache table.

Click [here](/articles/19_Broadway/actors/07_masking_and_sequence_actors.md) to read how to use fabric's masking Broadway actors.

#### Customized Masking Logic 

K2view enables users to create their own masking functions:
- The **MaskingLuFunction** Broadway actor can be used to call a customized function (a shared function or an LU's function) to mask the required field.  
- The **MaskingInnerFlow** Broadway actor can be used to call a customized Broadway flow to mask the required field.

The use of **MaskingLuFunction** and **MaskingInnerFlow** actors guarantees the usage of the K2view masking mechanism including the **SHA-512 hashing** and the caching.  The user does not need to handle them by their customized function.

### Masking Actors Properties

#### Target Value Uniqueness

- The user can decide whether the masked value is unique per original value (hashed value) or if it can be used for more than one original value. For example, a masked SSN must be unique, but a masked Family Name can be the masked value of different original values. 

#### Cache with Expiration date

- Each cached link of hashed value to masked value can have a TTL (Time To Leave). This link will expire once the TTL is reached, and the original value will be masked again

#### Caching Level Parameters

- The caching of the masked values can be saved on different levels based on the user’s input. Each one of the following parameters can be enabled or disabled from being part of the **Caching key**:
  - Instance ID
  - Target Environment
  - Execution ID

## K2view Masking Advantages

- Supports **cross instances consistency** based on the hashed values.
- The original value is not used as input for creating the random masked value, other than formatting purposes.
- **In memory** processing. The MicroDB is created with the masked values.
- Using the Fabric Masking mechanism (using **SHA-512** algorithm).
- **Multiple masking options** to enable a maximal flexibility when masking the data.

## De-Anonymization (Pseudonymization)

In some cases there is a business need to get the original value of the masked LUI. For example, get the mail address to contact the customer. 

There are two recommended approaches to support de-anonymization and get the original value of the masked field: 

- Keep the source Instance ID in Fabric and use it to retrieve the original data from source system.

- Keep the encrypted version (each Instance is encrypted separately) of the original values in *Fabric only*, in addition to the anonymized values. Limit the access to the anonymized data only. Only permitted users can access the original values.

Click [here](/articles/26_fabric_security/03_fabric_LUI_encryption.md) for more information about the LUI encryption.

[![Previous](/articles/images/Previous.png)](/articles/26_fabric_security/05_fabric_webservices_security.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/26_fabric_security/07_user_IAM_overview.md)

