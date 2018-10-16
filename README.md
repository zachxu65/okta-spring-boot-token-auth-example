# Simple Token Authentication with Java
 
An example app that shows you how to do token authentication with Java and Spring Boot.

Please read [Simple Token Authentication for Java Apps](https://developer.okta.com/blog/2018/10/16/2018-10-16-token-auth-for-java) to see how this app was created.

**Prerequisites:** [Java 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

> [Okta](https://developer.okta.com/) has Authentication and User Management APIs that reduce development time with instant-on, scalable user infrastructure. Okta's intuitive API and expert support make it easy for developers to authenticate, manage, and secure users and roles in any application.

* [Getting Started](#getting-started)
* [Links](#links)
* [Help](#help)
* [License](#license)

## Getting Started

To install this example application, run the following commands:

```bash
git clone https://github.com/oktadeveloper/okta-spring-boot-token-auth-example.git
cd okta-spring-boot-token-auth-example
```

This will get a copy of the project installed locally. To install all of its dependencies and start the app, run:
 
```bash
./gradlew bootRun
```

### Create an Application in Okta

You will need to create an OpenID Connect Application in Okta to get your values to perform authentication. 

Log in to your Okta Developer account (or [sign up](https://developer.okta.com/signup/) if you don’t have an account) and navigate to **Applications** > **Add Application**. Click **Web**, click **Next**, give the app a name you’ll remember, and select "Client Credentials". Click **Done** and copy the `clientId` and `clientSecret` into `src/main/resources/application.yml`. 

```yaml
server:  
  port: 8080  
                                         
okta:  
  oauth2: 
    issuer: https://{yourOktaDomain}/oauth2/default  
    clientId: {yourClientId}
    clientSecret: {yourClientSecret}
```

**NOTE:** The value of `{yourOktaDomain}` should be something like `dev-123456.oktapreview`. Make sure you don't include `-admin` in the value!

After modifying this file, restart your app and you should be able to authenticate with an access token. Please read the [companion blog post](https://developer.okta.com/blog/2018/10/16/2018-10-16-token-auth-for-java) for additional information.

## Links

This example uses [Okta's Spring Boot Starter](https://github.com/okta/okta-spring-boot).

## Help

Please post any questions as comments on the [blog post](https://developer.okta.com/blog/2018/10/16/2018-10-16-token-auth-for-java), or visit our [Okta Developer Forums](https://devforum.okta.com/). You can also email developers@okta.com if you would like to create a support ticket.

## License

Apache 2.0, see [LICENSE](LICENSE).
