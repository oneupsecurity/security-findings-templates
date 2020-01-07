# Title

Authentication Tokens Disclosed to Unauthenticated Users

# Risk
[TKTK Update risk based on what's disclosed.]

# Executive Summary

The [TKTK application name] application discloses [TKTK authentication tokens] to [TKTK unauthenticated users, authenticated users]. Attackers can use this information to [TKTK steal documents belonging to other users]

# Description

Authentication tokens are used to TKTK.

When [TKTK requesting the profile of a user], the [TKTK user's, meeting] authentication token is disclosed. 


The following HTTP request is sent to the server:

~~~
[TKTK HTTP Request]
~~~

The following HTTP response was received. Note how the response body contains the user's authentication token.

~~~
[TKTK Response]
~~~



The following [TKTK application name] application's code discloses authentication tokens. [TKTK Explain what the code does, such as the user object is serilaized, which includes the user's authentication token, and is returned in the response.]

~~~
[TKTK Replace me with source code

131 return user.getCurrentAuthenticationToken()
~~~

# Proof of Concept

[TKTK TODO]

# Remediation

Do not disclose authentication tokens to unauthorized users.

# References

"OWASP Top 10-2017 A2-Broken Authentication" - https://www.owasp.org/index.php/Top_10-2017_A2-Broken_Authentication
"CWE-200: Information Exposure" -  https://cwe.mitre.org/data/definitions/200.html
