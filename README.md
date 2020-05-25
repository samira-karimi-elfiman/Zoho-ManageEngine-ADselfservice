# Zoho-ManageEngine-ADselfservice

# Application: ADselfservice plus web
# Notification Date: May 17, 2020

# What was the Problem?
low level user can send admin request related to multi factor authentication And create the following problems:
1. multi-factor authentication settings disable for all assets
2. registration of security question become Mandatory for all users
3- security question authenticator enable for ADSelfService Plus login
4- Everyone loses access to the account, even the admin

# Effected Products:
ADselfservice plus Version less than < 5815
How do I fix it?
This has been fixed on Version 5816. To apply this fix, download the latest version (5817)

# Exploit:

note :
you can find Admin and user demo panel in internet "https://demo.adselfserviceplus.com/authorization.do" and test admin demo panel requests with user  

1- login to ADSelfService with your domain account with low level user
2- in demo admin panel/configuration/multi-factor authentication/MFA-TFA Settings
   tick "Enforce these authenticators during enrollment" and in drop-down menu tick "security questins"
   tick "Enable authenticators for ADSelfService Plus login" and in drop-down menu ticked "security questions"
3- click on "save settings" , and in burp intercept this request
4- sent that request with yours domain and cookie user, in response, you will see "{"sSTATUS":"Settings saved successfully."}"  
5- in login:
   security question enrollment become mandatory for all users
   multi-factor authentication settings disable for all assets
   security question authenticator enable for ADSelfService Plus login
   Everyone loses access to the account,even the admin
