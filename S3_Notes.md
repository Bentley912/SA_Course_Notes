# S3_Notes

* S3 is object based ie allows you to upload files. 

* Files can be for 0 Bytes to 5 TB
* There is unlimited storage
* Files are stored in Buckets (Folder)
* Buckets have universal names spaces,names must be unique globally
* https://s3-eu-west-1.amazonaws.com/{bucketname}
* Read after Write conssitency for PUTS of new Objects
* Eventual COnsistecy for overwirte PUTS and DELETS(can take some time)

### Storage Tiers

* S3 Standard : 99.99% Availibility, 11 9s durability. 

* S3-IA - (Infrequently Accesed): less frequenmt access. Lower fee but charged retrieveal fee

*S3 One ZONe-IA - lower cost but no Multiple Availibility Zone

* Glacier - Archival. 3- 5 hours

### Core FUndamentals 

* Key (name)
* Value (data)
* Version ID
* Metadata
* Access Control Lists

### Versioning

* Stores all versions fo an object(invludeing all writes) You pay for all versions. 10 Version of 1 GB File = 10 GB of Billing

* Once enabled, Versioning Cant BE disable

* Integrates LifeCycle Rules

### Life_CYle Mgmt

* Can be used independent of Versioning

* Transition to S3-IA ( >= 128kb and 30 days old)

* archive to glacier

* delete

### Cloudfront

* Edge Location - This is the location where content will be cached

* Origin - origin of the files that will be distributed. This can be s# bucket, EC2 INstance, ELB or ROute53

* Distribution- name givient ot the CDN which will consist of collection of Edge Locations

 --* Web distribution
 --*  RTMP - USed for Media Streaming


 * Edge location can be read or writtien to 

 * OB ject are cached for TTL (Time to Live) Default is 24 hours

 * You can clear cache objects, but you will be charged

 ### Securing BUckets

* By default, all newly buckets are PRIVATE

* You can set up acces control to buckets using : Bucket Policies and Accesss Control Lists

* S3 can be configured to create access logs whihc log request to the bucket 

### Encryption

* In Transit --> SSl/TLS

* At REst 
    * Server Side Encryption --> S3 Managed Keys -SSE -S#
    * AWS KEt managed Service --> SSE- KMS
    * Server SIde Encryptin with Customer Provided Keys -SSE0C

* Client Side Encryption

### Storage Gateway

* File Gateway - Flat files, sotred on S#

* Volume Gatrway
    * Stored Valumes - Entrie dataset is stored on site and is asycnhronously backeed up to S3

    * Cached Volumes - Entired Data set is stored and frequently accessed data is cached on site

* Gateway Virtual Tape Library 
    * USed for backup and uses popular back up apps like NetBackup, BackupExec, Veeam etc



