----------------------------------------------------------------------------------Project Features ---------------------------------------------------------------------------------------

Our solution encompasses the following key components:
Amazon S3 Integration: Seamless integration with Amazon S3 enables the uploading and storage of public policy prospectus documents. A RAG (Retrieval-Augmented Generation) framework is implemented to extract contextual information, empowering insurance agents to respond effectively to end-user queries via Agentforce, built on Salesforce Data Cloud. Additionally, AWS Lambda functions have been developed to automate the ingestion of files from S3 into Salesforce Data Cloud.


Slack Integration: Integration of Salesforce Agentforce with Slack facilitates real-time, interactive decision-making, enhancing operational efficiency and agent responsiveness.


Community Site Integration: Agentforce is also integrated with the customer-facing community site to ensure a unified and consistent user experience.


Image-Based Damage Assessment: Leveraging a Convolutional Neural Network (CNN) built using the PyTorch library in Python, our system detects and evaluates the severity of vehicle damage from images, contributing to a faster and more accurate claims assessment process.



----------------------------------------------------------------------------------Data Cloud Details ---------------------------------------------------------------------------------------

Data Cloud details  -  
2x UDLO (Auto Insurance & Life Insurace) - for Unstrucuted data (pdf's uploaded to S3). Also respective UDMO created along with Chunk object.
SOQLs -
SELECT SourceRecordId__c, Chunk__c, ChunkSequenceNumber__c, DataSourceObject__c, InternalOrganization__c, KQ_RecordId__c, KQ_SourceRecordId__c, RecordId__c FROM Auto_Insurance_chunk__dll
SELECT SourceRecordId__c, Chunk__c, ChunkSequenceNumber__c, DataSource__c, DataSourceObject__c, InternalOrganization__c, KQ_RecordId__c, KQ_SourceRecordId__c, RecordId__c FROM Life_Insurance_chunk__dll ORDER BY SourceRecordId__c DESC

2x Search Index for Vectorization
3x Einstein retrivers (2 default and 1 custom built for contact extraction from Pdfs like email, website, phone etc.)
3x Prompt Templates.
1x Agentforce (Insurace Agent)


----------------------------------------------------------------------------------AWS Details ---------------------------------------------------------------------------------------

S3 Bucket - https://ap-southeast-2.console.aws.amazon.com/s3/buckets/insuranceproductsdir?region=ap-southeast-2&bucketType=general&tab=objects   (Not public access after login only creds below)
Lambda funtion for Data Cloud Unstructred Ingestion present. Guide followed - https://developer.salesforce.com/docs/data/data-cloud-int/guide/c360-a-awss3-udlo.html
S3 Connector also made in Salesforce.

----------------------------------------------------------------------------------CREDS ---------------------------------------------------------------------------------------

Salesforce Org Creds
URL: https://login.salesforce.com
Username: epic.6991cc22b661@orgfarm.com
Password: orgfarm1234

AWS Creds for Root User 
Email - shobhandasrulez@gmail.com
Password - SFDC@ncino123



----------------------------------------------------------------------------------Damage Detection Python Code/ Details ---------------------------------------------------------------------------------------


CODE -  https://github.com/Shobhan-Das-SFDC/tdx-agentforce
Library for CNN Image Processing - 
torch
torchvision

Use post man to test after deployment. Deployment details in Readme.txt file in the above repo.





