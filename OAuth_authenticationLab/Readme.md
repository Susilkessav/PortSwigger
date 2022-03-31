# OAuth 2.0 authentication vulnerabilities

While browsing the web, you've almost certainly come across sites that let you log in using your social media account. The chances are that this feature is built using the popular OAuth 2.0 framework. OAuth 2.0 is highly interesting for attackers because it is both extremely common and inherently prone to implementation mistakes. This can result in a number of vulnerabilities, allowing attackers to obtain sensitive user data and potentially bypass authentication completely.

In this section, we'll teach you how to identify and exploit some of the key vulnerabilities found in OAuth 2.0 authentication mechanisms. Don't worry if you're not too familiar with OAuth authentication - we've provided plenty of background information to help you understand the key concepts you'll need. We'll also explore some vulnerabilities in OAuth's OpenID Connect extension. Finally, we've included some guidance on how to protect your own applications against these kinds of attacks.

# How does OAuth 2.0 work?
OAuth 2.0 was originally developed as a way of sharing access to specific data between applications. It works by defining a series of interactions between three distinct parties, namely a client application, a resource owner, and the OAuth service provider.

Client application - The website or web application that wants to access the user's data.
Resource owner - The user whose data the client application wants to access.
OAuth service provider - The website or application that controls the user's data and access to it. They support OAuth by providing an API for interacting with both an authorization server and a resource server.
There are numerous different ways that the actual OAuth process can be implemented. These are known as OAuth "flows" or "grant types". In this topic, we'll focus on the "authorization code" and "implicit" grant types as these are by far the most common. Broadly speaking, both of these grant types involve the following stages:

The client application requests access to a subset of the user's data, specifying which grant type they want to use and what kind of access they want.
The user is prompted to log in to the OAuth service and explicitly give their consent for the requested access.
The client application receives a unique access token that proves they have permission from the user to access the requested data. Exactly how this happens varies significantly depending on the grant type.
The client application uses this access token to make API calls fetching the relevant data from the resource server.
Before learning how OAuth is used for authentication, it's important to understand the fundamentals of this basic OAuth process. If you're completely new to OAuth, we recommend familiarizing yourself with the details of both of the grant types we're going to cover before reading further.
