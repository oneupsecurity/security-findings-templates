# Title

Authentication Tokens Passed In URLs

# Risk
Low

# Executive Summary

The [TKTK application name] application passes authentication tokens in URLs. Attackers can impersonate targeted users by obtaining their valid authentication tokens.

# Description

Authentication tokens passed through URLs are susceptible to accidental disclosure. Attackers who steal authentication tokens of users can impersonate the targeted users.  Attackers may gain access to authentication through various attack vectors, such as [TKTK viewing a user's browsing history, obtaining URLs leaked in emails when copied or pasted, or obtaining HTTP request server logs].  

The [TKTK application name] application uses [TKTK JSON Web Tokens, Session Identifiers] in URLs to identify users.  The following HTTP request is sent to [TKTK https://example.com?token=REDACTED ] when a user [TKTK authenticates in, registers]. The authentication token has been redacted to mitigate accidental disclosure.

*HTTP Request:*

~~~
[TKTK TODO REPLACE ME]
~~~

Following is the source code from the [TKTKTK application] which [TKTK inserts/processes] authentication tokens in URLs.

From *[TKTK Path]:*


The following additional locations disclose authentication tokens in URLs:

| URL | Description |
|-----|-------------|
| [TKTK https://example.com/auth?=123] | [TKTKK When logging into the system, HTTP request is sent to URL.] |

# Proof of Concept

[TKTK TODO]

# Remediation

Passing authentication tokens through HTTP header values or POST bodies is recommended.  Avoid passing authentication tokens through URLs. 

# References

"Top 10-2017 A3-Sensitive Data Exposure" - https://www.owasp.org/index.php/Top_10-2017_A3-Sensitive_Data_Exposure
