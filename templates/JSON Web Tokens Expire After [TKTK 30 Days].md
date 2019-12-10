# Title

JSON Web Tokens Expire After [TKTK 30 days]

# Risk
Low

# Executive Summary

The [TKTK application name] application issues JSON Web Tokens which expire [TKTK 30 days after being issued].  Attackers can impersonate targeted users by obtaining their unexpired authentication tokens.

# Description

Authentication tokens which expire after long periods of time are more susceptible of being compromised. Attackers may gain access to authentication tokens or force used to perform authenticated requests through [TKTK various attack vectors such as cross-site scripting, viewing a user's browsing history, obtaining URLs leaked in emails when copied or pasted, or obtaining HTTP request server logs].  

When authenticating successfully against the [TKTK application] application as the user [TKTKTK user], the following HTTP request and response were sent and received. 


*HTTP Request:*

~~~
[TKTK Place Request Here. Redact sensitive information as necessary, such as JWT signature.]
~~~

*HTTP Response:*

~~~
[TKTTK Place Response Here. Redact sensitive information as necessary, such as JWT signature.]
~~~

Following is the base64 decoded JSON Web Token from the above HTTP response. Note how the token is valid for [TKTK 30 days] after it is issued.

~~~
[TKTK decoded json-web token]
~~~

Following is the source code from the [TKTKTK application] which [TKTK sets/checks the JSON Web Token expiration time].

From *[TKTK Source Code PathPath]:*

~~~
[TKTK Put Sourcecode Here]
~~~

# Proof of Concept

[TKTK TODO]

# Remediation

Based on business and security requirements, determine and enforce the period in which authentication tokens are valid. As a recommendation, authentication tokens should be valid for at most [TKTKTK 4] hours and expire after [TKTKTK 15] minutes of inactivity. A user's authentication token must expire immediately when the user requests to sign out.

# References

"Top 10-2017 A2-Broken Authentication" - https://www.owasp.org/index.php/Top_10-2017_A2-Broken_Authentication
