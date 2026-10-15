Version: NAFATH-V2

Track: Data

## Overview
A reliable 5G service for emergency responders depends on several technology fields working together. Software must handle requests safely when network failures cause clients to retry them. AI can help predict congestion, but its models need proper evaluation to avoid overfitting. Mobile applications should support offline work and synchronize data when connectivity returns. Networking technologies, such as 5G network slicing, can help provide dedicated resources for emergency services. Cybersecurity is essential for detecting attacks, responding to incidents, and restoring affected services. Finally, data systems help operators organize service information and produce useful reports. These six fields are connected: reliable software, intelligent predictions, resilient mobile apps, effective networking, strong security, and well-organized data all contribute to maintaining service availability during emergencies.

## Software
Safe methods do not request changes to the server's state. GET, HEAD, OPTIONS and TRACE are safe methods. Idempotent methods have the same intended effect when repeated as when sent once. This matters when a connection fails before a response arrives: an idempotent request can be retried more safely, while retrying POST blindly may create duplicate records. All safe methods are idempotent, as are PUT and DELETE.

Resource: RFC 9110 - HTTP Semantics - https://www.rfc-editor.org/rfc/rfc9110.html
  
## AI
Overfitting occurs when a model learns the training data too closely, including its noise, which leads to poor performance on new data. Cross-validation helps detect this by dividing the data into folds. The model is trained on some folds and evaluated on the remaining fold, and the scores are compared. If the model performs well on training data but poorly on validation data, this may indicate overfitting. For congestion forecasting, a model that memorizes past traffic may fail during unusual events like disasters.

Resource: Cross-validation: evaluating estimator performance - https://scikit-learn.org/stable/modules/cross_validation.html

## Mobile
The app should support offline functionality so responders can access important information when the network is unavailable. It can store data locally and allow responders to record updates without an internet connection. Changes made offline can wait in a queue and be sent to the server when connectivity returns. The app should also handle conflicts when different users update the same record, helping keep information consistent and reducing the risk of data loss.

Resource: Build an offline-first app - https://developer.android.com/topic/architecture/data-layer/offline-first

## Networking
5G network slicing divides a shared physical network into logical networks with different capabilities and characteristics. Each slice can be tailored to specific service requirements through a Service Level Agreement (SLA) and may use dedicated or shared resources. For emergency responders, a dedicated slice can be configured to provide suitable capacity and isolate resources from other slices. This can help maintain communication during network congestion, depending on how the operator configures and manages the network.

Resource: Generic Network Slice Template (NG.116) - https://www.gsma.com/newsroom/wp-content/uploads/NG.116-v3.0.pdf

## Cybersecurity
Incident response helps an organization manage cyberattacks and reduce their impact. Govern, Identify and Protect prepare the operator through risk management. Detect finds and analyzes attacks, such as abnormal traffic on the emergency slice. Respond contains the incident, for example by blocking malicious traffic while prioritizing emergency communications. Recover restores affected systems and services. Lessons learned then help improve future security practices.

Resource: SP 800-61 Rev. 3, Incident Response Recommendations and Considerations for Cybersecurity Risk Management - https://csrc.nist.gov/pubs/sp/800/61/r3/final

## Data
A star schema connects a central fact table to dimension tables, such as date and region. A snowflake schema splits dimension data into additional related tables to reduce repeated information. For 5G service usage reports per region per day, a star schema is a suitable choice because its simpler structure makes it easier to filter, group, and summarize usage data by date and region.

Resource: Understand star schema and the importance for Power BI - https://learn.microsoft.com/en-us/power-bi/guidance/star-schema

## Misconception in My Track
A common misconception is that a reporting database can keep everything in one table, mixing measurements with descriptions of region and date. In reality, a good model separates the roles: dimension tables enable filtering and grouping, while fact tables enable summarization. For example, a usage report per region per day can use a fact table of usage measurements linked to date and region dimensions. The Microsoft Learn section "Star schema relevance to Power BI semantic models" advises avoiding mixing the two types in one table.

## Open Question
How can the operator use daily 5G usage data to predict congestion in specific regions before it affects emergency responders, and would daily data provide enough detail for timely predictions?
