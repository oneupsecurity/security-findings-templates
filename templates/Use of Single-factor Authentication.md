# Title
Use of Single-factor Authentication

# Risk
Low

# Description


The [TKTK application name] application uses Single-factor Authentication. The risk of accounts becoming compromised due to the use of Single-factor authentication is greater when compared to the use of Multi-Factor Authentication.

Multi-factor authentication requires users to provide two or more factors from different categories to prove their identity. Factors are commonly categorized into three types; something you know (e.g password/pin), something you have (e.g smartcard/security token generator), and something you are (e.g. fingerprint/face). By requiring two-or-more valid factors to authenticate with a system, attackers need access to additional pieces of information in order to log in.  Relying solely on user-generated passwords for authentication is not recommended, as users typically re-use passwords for multiple systems, which increases the risk of their credential becoming compromised.

Following is the [TKTKK application name] application's code which handles authentication.  On line [TKTK 31] , the application authenticates the user using only a [TKTK password]. 

From [TKTK  URL , the method *SomeController.displayPosts()* defined in *filePath* , the function *displayPosts()* defined in *filePath*, etc]:
~~~
[ TKTK Place code snippet here with numbered lines. Ex:

  313 logInUser(user,password)
]

~~~

# Proof of Concept

[TKTK Explain Reproduction Steps. Paste request/responses, or explain actions taken through website to exploit,etc.]


# Recommendations

If possible, require all users to use Multi-factor authentication, especially administrative accounts. Using SMS messages to deliver one time passwords for a second form of authentication is not recommended. Attacks against the SS7 protocol exist, which allows attackers to re-route phone numbers. Attackers may gain access to a user's phone number by social-engineering telephone companies to assign them the target user's phone number. The use of a One Time Password generation application is recommended over One Time Passwords delivered over SMS messages.

# References
"OWASP Top 10-2017 A2-Broken Authentication" - https://www.owasp.org/index.php/Top_10-2017_A2-Broken_Authentication
"OWASP Testing Multiple Factors Authentication (OWASP-AT-009) " - https://www.owasp.org/index.php/Testing_Multiple_Factors_Authentication_(OWASP-AT-009)
"CWE-308: Use of Single-factor Authentication" - https://cwe.mitre.org/data/definitions/308.html
