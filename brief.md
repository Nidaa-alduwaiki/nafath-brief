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

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
