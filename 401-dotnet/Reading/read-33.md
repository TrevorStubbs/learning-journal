# Readings: OAUTH

- [OAUTH MSFT Docs](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/social/?view=aspnetcore-2.1&tabs=visual-studio)
- [OAUTH](https://www.jerriepelser.com/blog/authenticate-oauth-aspnet-core-2/)

## OAUTH in ASP.NET
- It's convenient for the end user.
- It shifts the complexities and the responsibilities to a 3rd party.

### Use SecretManager to store tokens assigned by login providers.
- [Facebook](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/social/facebook-logins?view=aspnetcore-3.1&viewFallbackFrom=aspnetcore-2.1) instructions
- [Twitter](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/social/twitter-logins?view=aspnetcore-3.1&viewFallbackFrom=aspnetcore-2.1) instructions
- [Google](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/social/google-logins?view=aspnetcore-2.1) instructions
- [Microsoft](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/social/microsoft-logins?view=aspnetcore-3.1&viewFallbackFrom=aspnetcore-2.1) instructions
- [Other provider](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/social/other-logins?view=aspnetcore-2.1) instructions


- in Startup.cs
``` Csharp
services.AddAuthentication()
    .AddMicrosoftAccount(microsoftOptions => { ... })
    .AddGoogle(googleOptions => { ... })
    .AddTwitter(twitterOptions => { ... })
    .AddFacebook(facebookOptions => { ... });
```

### Authenticate with OATH
> 1. The Consumer makes a request to the Service Provider authorization endpoint to authorize the user.
> 1. The Service Provider authenticates the user and prompts them whether to authorize the Consumer to access their information.
> 1. If the user authorizes the Consumer, the Service Provider redirects back to the redirect URI on the Consumer’s website with a temporary access code.
> 1. The Consumer calls the token endpoint on the Service Provider website to exchange the code for a more permanent access token.
> 1. The Service Provider grants an access token which can be used to authenticate subsequent requests to protected resources 
<sub>Jerrie Pelser</sub>

