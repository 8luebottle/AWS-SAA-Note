# AWS Cognito
> Amazon Cognito provides authentication, authorization, and user management for your web and mobile apps.

![AWS Cognito](https://user-images.githubusercontent.com/48475824/145217152-729eae7b-2497-46b3-bdab-6b725a5a73de.png)

- Cognito is decentralized managed authentication system.

- Easily add authentication to your mobile and desktop App. ⇒ Cognito

- [`User Pools`][user-pools]:

  ![AWS User Pools](https://user-images.githubusercontent.com/48475824/145217478-dc5915f7-02d0-44f2-b742-7e4fe17b9dbe.png)

  - user directory, allows users to authenticate using OAuth to IdP
    - IdP: Facebook, Google, Amazon to connect to web-applications.
  - Cognito User Pool is in itself a IdP.
    - all about User Name, Password, User Registration, Account Recovery
  - use JWTs for to persist authentication.

- [`Identity Pools`][identity-pools]:
  - provide temporary AWS credentials to access services.  
    e.g. S3, Dynamo DB

- [`Cognito Sync`][cognito-sync]:
  - can sync user data and preferences across devices with one line of code. (Powered by SNS)

- [`Web Identity Federation`][web-identity-fed]:
  - exchange identity and security information between an IdP(Identity provider) and an App.

    - `Identity Provider`: a trusted provider of your user identity that lets you use authenticate to access other services.

      - [`OIDC`][oidc] is a type of Identity Provider which uses OAuth  
        - OIDC stands for OpenID Connect providers

      - [`SAML`][saml] is a type of Identity Provider which is used for Single Sign-on.  
          SAML 2.0

<!-- Labeling -->
[user-pools]: https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html
[identity-pools]: https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-identity.html
[cognito-sync]: https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-sync.html
[web-identity-fed]: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_oidc.html
[oidc]: https://docs.aws.amazon.com/cognito/latest/developerguide/open-id.html
[saml]: https://docs.aws.amazon.com/cognito/latest/developerguide/saml-identity-provider.html
