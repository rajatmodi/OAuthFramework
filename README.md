# Use Case I want to support.

## UseCase A

* `End-User` is playing Candy Crush on a Web_App/Desktop_App/ANY_OTHER_CLIENT. `Client`
* `End-User` creates a highscore and `Client` wants to post this event on `End-User` Facebook Wall.
* `End-User` agrees to this post and provides the Facebook username for the same.
* `Client` requests Facebook `Resource Server` to create a Post on `End-User` wall on his/her behalf.
* **`Resource Server` has to authenticate the `Client`.**
* **`Resource Server` has to authorise this request that originated from `Client`.**
*  After Authenticating and Authorising the `Client` for this action the Post on the Facebook wall is created.

## UseCase B (Service-Oriented-Architecture)
Services encapsulate Business Logic. Here the *Protected Resource* is the Business Logic. The `Resource Owner` is the Service Owner. `Client` is another service who intends to utilize the business logic and add more functionality around that. 
`Resource Server` is the Service itself. 

* `ServiceA` wishes to send an SMS congratulating the winners of a contest.
* `ServiceB` has an API `getWinners` to return the list of emailIDs that won the contest.
* `ServiceA` calls `ServiceB` to getWinners.
* **`ServiceB` has to Authenticate `ServiceA`.**
* **`ServiceB` has to Authorize `ServiceA`.**


*My Target is to define the Mechanism to achieve the **BOLD** statements in above UseCases.*


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

## Sequence Diagrams

![Obtaining Access Token](https://user-images.githubusercontent.com/14327075/68687025-91efd700-0592-11ea-90ea-035618057f23.png)

                         Authorization Code Flow (https://tools.ietf.org/html/rfc6749#section-4.1)

     +----------+
     | Resource |
     |   Owner  |
     |          |
     +----------+
          ^
          |
         (B)
     +----|-----+          Client Identifier      +---------------+
     |         -+----(A)-- & Redirection URI ---->|               |
     |  User-   |                                 | Authorization |
     |  Agent  -+----(B)-- User authenticates --->|     Server    |
     |          |                                 |               |
     |         -+----(C)-- Authorization Code ---<|               |
     +-|----|---+                                 +---------------+
       |    |                                         ^      v
      (A)  (C)                                        |      |
       |    |                                         |      |
       ^    v                                         |      |
     +---------+                                      |      |
     |         |>---(D)-- Authorization Code ---------'      |
     |  Client |          & Redirection URI                  |
     |         |                                             |
     |         |<---(E)----- Access Token -------------------'
     +---------+       (w/ Optional Refresh Token)

   Note: The lines illustrating steps (A), (B), and (C) are broken into
   two parts as they pass through the user-agent.

## Out of Scope for OAuth Framework
* The use of OAuth over any protocol other than HTTP is out of scope.
* Authenticating resource owners to clients is out of scope for this specification. 
* The interaction between the authorization server and resource server is beyond the scope of this specification.
* Access token attributes and the methods used to access protected resources are beyond the scope of
  this specification and are defined by companion specifications such
  as [RFC6750] https://tools.ietf.org/html/rfc6750.
* The means through which the client registers with the authorization server are beyond the scope of this
  specification but typically involve end-user interaction with an HTML registration form.  
* The methods used by the resource server to validate the access token (as well as any error responses)
  are beyond the scope of this specification but generally involve an
  interaction or coordination between the resource server and the
  authorization server.    
                     

## Functional Requirements
[PLACEHOLDER]

## Non Functional Requirements

[PLACEHOLDER]

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

