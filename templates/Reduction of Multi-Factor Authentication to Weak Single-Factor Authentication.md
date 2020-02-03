# Title

Reduction of Multi-Factor Authentication to Weak Single-Factor Authentication

# Risk
High

# Description

The [TKTK application name] application solely relies upon [TKTK SMS] messages for [TKTK passwords resets]. Attackers who can intercept [TKTK SMS] messages can [TKTK intercept SMS messages and reset passwords of targeted users].

The SS7 protocol contains known vulnerabilities which attackers used to intercept calls and SMS messages. Attackers can also be re-assigned phone numbers of targeted users through social-engineering telecommunication providers. The [TKTKTK application name] application delivers One-time Passwords over [TKTKTK SMS, telephone calls] for account verification.] This increases the risk that attackers can [TKTK intercept the codes to gain unauthorized access to targeted user accounts].

Following is the [TKTKK application name] application's code which handles authentication.  On line [TKTK 31] , the application authenticates the user using only a [TKTK one-time password delivered over SMS]. 

From [TKTK  URL , the method *SomeController.displayPosts()* defined in *filePath* , the function *displayPosts()* defined in *filePath*, etc]:
~~~
[ TKTK Place code snippet here with numbered lines. Ex:

  313 resetPassword(user,newPassword,oneTimePassword)
]

~~~

# Proof of Concept

[TKTK Explain Reproduction Steps. Paste request/responses, or explain actions taken through website to exploit,etc.]


# Recommendations

Use a security vetted authentication framework.

Password resets should require users to prove their identity, to a level which is acceptable based on security and business requirements. Typical systems require users to follow an email password reset links, and to supply a valid one-time password.

# References
"OWASP Top 10-2017 A2-Broken Authentication" - https://www.owasp.org/index.php/Top_10-2017_A2-Broken_Authentication
"CWE-308: Use of Single-factor Authentication" - https://cwe.mitre.org/data/definitions/308.html
"An Empirical Study of Wireless Carrier Authentication for SIM Swaps" - https://www.issms2fasecure.com/assets/sim_swaps-01-10-2020.pdf
