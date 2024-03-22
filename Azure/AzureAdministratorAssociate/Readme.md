# Overview
- Azure ru from Microsoft servers around the word
- 3 core element: compute, storage and networking
## Compute
- Virtual Machine - Infrastructure as a Service
- App Service - Platform as a Service
- Now use Azure Container Instane - ACI
    - Multiplle container - use Azure Kubernetes Service
- Azure function (less recommended) - Include individual functions
## Storage
- Blob storage: colection of files, Its have a flat stucture not hiarachy, typically use for raw data like videos, images.
    - Have multiplle access tier:

        |Type|Archive|Cool|Hot|
        |:-|:-|:-|:-|
        |Purposse|Rearly access files such as backup files|Files that expected to access once a month|Frequently access files|
        |Cost|Lowest|Medium|Highest|
        |Time for retrieval cost|Highest - several hours||
- Azure File Storage: Like SMB server or file share that can mount on Window servers
- Azure Data Lake Gen 2: for data analystic application
- SQL server database: most common use
- Azure Synapse Analystics: best choice for datawarehouse
- Azure Cosmos DB: application that abstract large amount of users. It's amazing database for large scale. However, it's not support all the features of relation database
- Azure Cache for Redis 
## Virtual Network (Vnet)
![Networking](CI_CX_INT\Azure\AzureAdministratorAssociate\Pictures "Networking")

