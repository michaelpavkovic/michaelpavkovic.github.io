---
layout: post
title:  "The Importance of Two Factor Authentication"
categories: hello world
---
#### Preface
Two Factor Authentication (a.k.a. 2FA) is the process of using, you guessed it, two forms of authentication on login. When a user logs into an account with 2FA disabled, the only means of security between them and a 'hacker' is their password. This can be dangerous for a number of reasons:

* __Keyloggers:__ A keylogger is a program that logs keystrokes on a keyboard. When a user enters their username and password into a login field, on a computer with keylogging malware, that password is now compromised. Without 2FA, so is the account. With 2FA, there is no problem, as the user can simply use their second form of authentication and be on their way.

* __Phishing Attacks:__ A phishing attack occurs when a user is lured into typing a username and password into a fake login field. These are most commonly delivered in the form of an email that is attempting to look real. For example, I could pretend to be Google, and send an email to an unsuspecting victim with a link telling them to login and, perhaps, update a phone number. In fact, only 33%<sup>[1](#footnote-1)</sup> of people check where emails came from, every time they receive a message.

* __Password Leaks:__ Countless breaches of corperations' password databases have occured in the last decade alone. Sony's Playstation Network and Adobe were two big ones. When a corperation's user password database is broken into, all of the accounts contained in it are compromised. With 2FA enabled, it doesn't matter whether the password was breached, as the user must still use a second, more secure form of authentication, to log in. Although, just as a tip, I still would strongly suggest to change your password to an account that was compromised by a huge password leak, even if you use 2FA.

#### Forms of 2FA
There are many forms of 2FA. Almost all of them use a password and username combo as a first factor of authentication. The second factor of authentication is what changes. Here are a few:

* __2FA App:__ The one I use, and I would assume most other 2FA users use, is an authenticator app on a cell phone. Google Authenticator is the most popular on Google Play, and it is fast. Its form of authentication is a six-didget code that changes every minute. Six didgets mean 1,000,000 combinations, which makes cracking the code in under a minute impossible, even if the password is already known. Many services work with it, including Google (obviously), and GitHub.

* __Physical USB Keys:__ These are much less common than the phone app, simply because not everybody has one already. The only downside is that they are costly, especially if it gets lost, and they may not work with as many services. If you want to buy one, Google reccomends this [key](https://www.amazon.com/Yubico-Y-123-FIDO-U2F-Security/dp/B00NLKA0D8) in their own documentation. I wouldn't mind using one, and they are extremly secure, as they cannot be replicated or spoofed, unlike a phone number.

* __Biometrics:__ This form of authentication is very rare, when paired with a password. Fingerprints, by themselves, are a popular way of signing into a cell phone, however they are very rarely used in conjunction with a password. Also, very few services support biometrics as a second factor of authentication. This method is very secure, as faking a fingerprint is nearly impossible when one doesn't have access to the finger itself, and the same goes for iris scanners, however the only device, that I know of, that has an iris scanner is the Samsung Galaxy Note7.

Enabling 2FA for many of your commonly used services, such as Google and GitHub, is very easy. Google calls theirs [2-Step Verification](https://www.google.com/landing/2step/), and GitHub's 2FA can be found in the user's Security settings. In the next blog post, I will discuss how to use 2FA with a GitHub account, since the method of pulling/cloning a Git repository is different when one cannot login simply with a password.

<p id="footnote-1"><a href="https://www.salesforce.com/blog/2013/07/email-marketing-stats.html">[1] Salesforce</a></p>