# Title

Concurrent User Sessions 

# Risk
Low

# Executive Summary

The [TKTK application name] application allows each user to have multiple active sessions. An attacker who is authenticated as a targeted user won't be signed out when the targeted user logs in.

# Description

Attackers may attempt to access to a user's session through various attack vectors, such as using a shared computer, brute-forcing credentials,  or stealing authentication tokens through Cross-Site Scripting. If a user is allowed to have multiple active sessions, an attacker authenticated attacker  will not be signed out when the target user logs in. [TKTK Additionally, as users are not notified when someone logs in to their account, or a session is attempted to be used from an untrusted device, the targeted user may not notice their account is compromised.]


[TKTK The following screenshot shows the user [TKTK exampleuser@exmaple.com] having two active sessions in different browser sessions:]

Place Screenshot Here

[TKTK Alternatively, show HTTP request and responses for logging in with the same user. Add another HTTP request and response showing the original session is still valid.]

The following [TKTK application name] application's code handles user authentication.  Note how active user sessions are not invalided. [TKTK additionally, note how the user is not notified of a successful login attempt].

~~~
[TKTK Replace me with source code]

131 return user.password.constantTimeEquals(passwordHash);
~~~

# Proof of Concept

[TKTK TODO]

# Remediation

If possible based on business requirements, allow each user to have only one active session. 

When a user authenticates, invalidate the user's previous sessions. Notify users of their last login time. If a session is attempted to be used from an untrusted device, do not allow the untrusted device to use the session, and notify the user of the failed authentication attempt, such as through email. 

Devices can be marked as trusted by generating and assigning a cryptographically secure high-entropy (such as 128 bits) token to a machine upon successful login. The token can be stored as a Cookie with appropriate flags to ensure it's transferred over secure channels, and not accessible by client-side scripts.

# References

"OWASP Top 10-2017 A2-Broken Authentication" - https://www.owasp.org/index.php/Top_10-2017_A2-Broken_Authentication
