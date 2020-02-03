# Title
Username Enumeration

# Risk
Low

# Description

The [TKTK application name] application discloses the registration status of usernames through [TKTK login error messages, HTTP response codes, etc.]. This allows attackers to perform more efficient brute-force attempts to gain unauthorized access to accounts.

Username enumeration occurs when a feature can be leveraged to determine the registration status of a username. Account registration status may be disclosed directly through server responses such as error messages, HTTP response codes, or HTTP redirects. Additionally, account registration status may be determined by side-channel attacks, such as measuring timing differences of processing HTTP requests with registered and non-registers usernames. Attackers who determine valid usernames can use the information to reduce the required search-space to brute force credentials for accounts. 

The [TKTK application name] application discloses the registration status of usernames through [TKTK login error messages, HTTP response codes, etc.]. [TKTK explain what was vulnerable and why. Ex, The user registration function displays an error message if a user already exists.] 

Following is code from the [TKTK application] application. On line [TKTK 31] , [TKTK a check is performed to see if the user exists. If the user does not exist, an error message is returned on line 35. If the user does exist, the user is notified to check their inbox]. This allows attackers to determine registered usernames.

From [TKTK  URL , the method *SomeController.displayPosts()* defined in *filePath* , the function *login()* defined in *filePath*, etc]:
~~~
[ TKTK Place code snippet here with numbered lines. Ex:

  313 if userExists(input):
  314   return "User Does Not Exist"
  315 else:
  316   logUserIn(username,password)
]

~~~

# Proof of Concept

[TKTK Explain Reproduction Steps. Paste request/responses, or explain actions taken through website to exploit,etc.]


# Recommendations

Differences which can be measured by attackers to determine registration status should be re-factored to remove measurable discrepancies.  

For instance, generic error messages should be returned to the user, which do not disclose registration status. For instance, login pages could display "Invalid username or password" whenever an invalid username or password is given. For registration or forgot password flows, a message such as "An email containing a password-reset link should be received shortly, if the account is registered" can be displayed.

To fix timing discrepancies, ensure the same amount required to process a request with registered and non-registered usernames is the same. This can be achieved by leveraging background tasks in registration and forgot password flows, and avoiding branching logic in authentication procedures whenever possible. For instance, the amount of time spent on database queries for registered and non-registered usernames should be the same. 


# References
"OWASP Top 10-2017 A2-Broken Authentication" - https://www.owasp.org/index.php/Top_10-2017_A2-Broken_Authentication
"CWE-203: Information Exposure Through Discrepancy" - https://cwe.mitre.org/data/definitions/203.html
