# jb-login-authenticator

⚠ This is still a (working) concept. Initial supporters will be able to determine features.
For now, it only works with classic (username/password) authentication.
Upon request and commitment, I'm willing to develop this so it could also work with for instance LDAP authentication.

Copyright (C) 2021 Jeffrey Bostoen

[![License](https://img.shields.io/github/license/jbostoen/iTop-custom-extensions)](https://github.com/jbostoen/iTop-custom-extensions/blob/master/license.md)
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/jbostoen)
🍻 ☕

Need assistance with iTop or one of its extensions?  
Need custom development?  
Please get in touch to discuss the terms: **jbostoen.itop@outlook.com**

## Pro extension
This extension was complex to develop and is now very feature rich, so this became a professional extension.
If you want to use this extension and get support, please get in touch to discuss the terms: **jbostoen.itop@outlook.com**


## What?
Adds two factor authentication to iTop.

The two factor authentication can be enforced on the person object (due to technical limitations, it's not on the user object).

Upon initial enforcement, users will be forced to set up their two factor authentication upon first log on with plain credentials.


## Screenshots

The user can directly enter the two factor code when authenticating to iTop using classic credentials.
![Login form - user can enter two factor code](screenshots/20210225_login.png)


If it's the first time and two factor authentication has been enforced in the backend, the user will have to set up a two factor code.
![Initial set up](20210225_first_setup_when_enforced.png)


The secret can be updated by the user (once authenticated) in the console (classic backend)
![Backend preferences](20210225_console_preferences.png)

The secret can be updated by the user (once authenticated) in the portal (modern frontend)
![Backend preferences](20210225_portal_preferences.png)

In the current concept (this can become more strict upon development requests!),  
people with access to the person object can configure two factor authentication to be enforced.
![Enforce two factor authentication](20210225_person.png)


# Guide
* See documentation included with extension


## Translations
* none yet


## Requirements
* iTop 2.7
* PHP 7.2 or newer

