# jb-login-authenticator

Copyright (C) 2021 - 2022 Jeffrey Bostoen

[![License](https://img.shields.io/github/license/jbostoen/iTop-custom-extensions)](https://github.com/jbostoen/iTop-custom-extensions/blob/master/license.md)
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/jbostoen)
🍻 ☕

Need assistance with iTop or one of its extensions?  
Need custom development?  
Please get in touch to discuss the terms: **info@jeffreybostoen.be** / https://jeffreybostoen.be

## Pro extension

This extension was complex to develop and is now very feature rich, so this became a professional extension.


## What?

This extension makes it possible for iTop users to login in a more secure way.   
After the traditional login with regular credentials, it requires a two factor code.  
Users get this TOTP code from their preferred authenticator app.

The extension allows iTop administrators or users with modify rights on the Person class to enforce the use of a two factor code.  
Otherwise, the use of two factor authentication remains optional. 

Upon enforcement, users will be required to set up their two factor authentication after logging in with their basic plain credentials.


It should work with:
* Authy
* Authenticator extension for MS Edge, FireFox and Google Chrome
* Google Authenticator
* Microsoft Authenticator
* any generic authenticator app


It should work with typical iTop configurations: built-in iTop users (UserLocal), LDAP users (UserLDAP) and externally authenticated users (UserExternal).  
Other types of users may work out of the box, but this is not guaranteed and untested.  
If needed, please consult before purchasing.

## Screenshots

The user can directly enter the two factor code when authenticating to iTop using classic credentials.  
![Login form - user can enter two factor code](screenshots/20210305_login.png)


If it's the first time and two factor authentication has been enforced in the backend,  
the user will have to set up a two factor code.  
![Initial set up](screenshots/20210305_first_setup_when_enforced.png)


The secret can be updated by the user (once authenticated) in the console (classic backend)  
![Backend preferences](screenshots/20210305_console_preferences.png)


The secret can be updated by the user (once authenticated) in the portal (modern frontend)  
![Portal preferences](screenshots/20210305_portal_preferences.png)


In the current concept (this can become more strict upon development requests!),  
people with access to the person object can configure two factor authentication to be enforced.  
![Enforce two factor authentication](screenshots/20210305_person.png)

# Features which will be developed upon sponsoring

* Send TOTP token to e-mail
* Send TOTP token to SMS services (API documentation will be requested!)
* Bypass based on HTTP header or IP ranges


# Guide

* See documentation included with extension


## Translations
* none yet


## Requirements

* iTop 2.7 or 3.0
* PHP 7.4 or newer

* iTop extensions
  * [jb-authenticationmethod](https://github.com/jbostoen/itop-jb-authenticationmethod)
  
  
## Known issues/limitations

* One two factor secret per person (even if this person has different user accounts)


## Cookbook

XML:
* add an value to an existing dropdown list (AttributeEnum)

PHP:
* enhancing iTop's login process using available hooks

## Requirements

PHP 7.4 or higher

## Credits

To generate QR-codes, the [chillerlan/php-qrcode](https://github.com/chillerlan/php-qrcode) package is used. 

The extension is also based on [PHPGangsta/GoogleAuthenticator](https://github.com/PHPGangsta/GoogleAuthenticator), released under a BSD-license.
It can generate secrets, generate codes, validate codes and present a QR-Code for scanning the secret.  
It implements TOTP according to RFC6238. A patch has been applied to make it compatible with Authy/Microsoft Authenticator/others.


## Feature ideas

Sponsor to speed up development of these features:

- [ ] Protection against Brute Forcing MFA (time-out, lock out indefinitely, ...)
- [ ] Trusted browser


## Sponsors

Special thanks to [PC-Notdienst](https://www.pc-notdienst.com/) for sponsoring the trusted networks feature.
