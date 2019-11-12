# OAuthFramework

## What is it?

* Authorisation Framework
* Enables clients to gain limited access to a Resource( Service/UserData) 
* Authorisation can be given by interacting with Resource Owner
* Authorisation can be given on behalf of the Client

## Challenges with password based Authentication

* Resources owner needs to provide credentials to clients where these creds can be compromised
* Service that is hosting the resource has to support password authentication
* Credentials limit us to implement access Control on the resource
* Credentials limit us implement expiration on the resource
* Revoking access for a particular client is not possible. Access for all clients will be revoked on password change

## Functional Requirements

Implement OAuth *Framework* for a Resource Server
https://tools.ietf.org/html/rfc6749#section-1.1

## Non Functional Requirements

None for Now. 

* Performance
* Scalability
* Capacity
* Availability
* Reliability
* Recoverability
* Maintainability
* Serviceability
* Security
* Regulatory
* Manageability
* Environmental
* Data Integrity
* Usability
* Interoperability

## Limitation
* OAuth works only with HTTP

![Obtaining Access Token](https://user-images.githubusercontent.com/14327075/68686802-36254e00-0592-11ea-8a81-a84c32a820e4.png)
