# Title

Personal Identifiable Information Disclosure

# Risk
Low

# Executive Summary

The [TKTK application name] application discloses personal identifiable information about its users without [TKTK requiring re-authentication, authorizing the user]. An attacker who [TKTK gains access to user accounts, brute forces database identifier of users] can obtain their [TKTKTK phone numbers, home addresses, driver's license numbers, social security numbers].

# Description

Personal Identifiable Information (PII) is any data which can be used to identify a person. Attackers may use PII to [TKTK commit identify fraud, locate home addresses of users, locate real-time locations of users].

When [TKTKTK viewing the profile of user@example.com], the following HTTP request and response was received from the endpoint [TKTKTK https://example.com]. The HTTP response discloses the user's [TKTKTK phone number, home address, driver's license number, social security number].

*HTTP Request:*

~~~
[TKTK Place Request Here. Redact sensitive information as necessary, such as JWT signature.]
~~~

*HTTP Response:*

~~~
[TKTTK Place Response Here. Redact sensitive information as necessary, such as JWT signature.]
~~~

Following is the source code from the [TKTKTK application name] application which discloses personal identifiable information.

From *[TKTK Source Code PathPath]:*

~~~
[TKTK Put Sourcecode Here]
~~~

# Proof of Concept

[TKTK TODO]

# Remediation

Do not disclose personal identifiable information of users whenever possible. If a user needs to view or update information, require the user to re-authenticate with the web application. For highly sensitive data, consider only allowing users to display the data, and never reading the data. Ensure all Personal Identifiable Information is protected by authenticated encryption. [TKTK Ensure authorization checks restrict users to accessing their own data.]

# References

"Top 10-2017 A3-Sensitive Data Exposure" - https://www.owasp.org/index.php/Top_10-2017_A3-Sensitive_Data_Exposure
