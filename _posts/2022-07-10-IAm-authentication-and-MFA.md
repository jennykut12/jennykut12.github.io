---
layout: post
title: How to explore the authentication options in AWS and MFA
subtitle: explore the authentication options in AWS and Multi-Factor Authentication
categories: Markdown
tags: [Markdown, journaling, blog, AWS, IAM, MFA, MultiFactorAuthentication, authentication]
---

# How to explore the authentication options in AWS and also Multi-Factor Authentication, or MFA.

With our user account called John. John wants to log into AWS. He does so through using his username and a password, and potentially an MFA token. Once he's then authenticated, he can then get access to the management console and perform operations in the console.

### What are the other methods of accessing AWS?

The other methods of accessing AWS are the CLI and the API and the SDK, which also leverages the API. When you access AWS by one of these methods, you use something called an access key ID and a secret access key. Which looks like bit more ugly, not as user friendly as a username and password. But these are then used in your code to authenticate to AWS and through to the API so that you can do whatever you want to do in AWS. These are known as access keys, and they're used for programmatic access. 

![datacamp certification](/assets/images/IAM%20authentication%20method.jpg)

### What is Multi-Factor Authentication or MFA?

 In IT security, we often talk about having different factors of authentication, and authentication is just proving who you are. So a way that you can do that is through something you know, and something you know is a password. If you log in to any kind of IT service using a username and password, the username is something which multiple people might know, but the password is something that you alone should know. So that's the secret, and that's the thing that proves that you are who you say you are.

Another factor of authentication is something you have. In this case, you have a physical device like a token or a device that generates a code, and only you can know that code and only because you have in your possession that physical device.

Lastly, there's something you are. This is biometrics like fingerprints or retina scans. And we don't use these in AWS, but we do use the first two. And that's why we have multiple factors of authentication.

So, in AWS, we use something you know, your IAM user account and a password and then something you have. And that's either a virtual MFA device such as Google Authenticator on your mobile phone or a physical MFA device, which is an actual physical token which cost money, whereas Google Authenticator is completely free.

Now, the physical tokens can be purchased from third parties. So when you go into the console, if you choose the option to actually use a physical token, you can see it there.You can see an option to click and purchase, but it will take you off to another website like Amazon.com.

![datacamp certification](/assets/images/Multifactor%20authentication.jpg)

![datacamp certification](/assets/images/Multifactor.jpg)

### So remember that for the exam. The physical tokens come from third parties.

## Enable Multi-factor Authentication (MFA)

###  Set up MFA for our user account.
1. Go into your Identity and Access Management console.
2. Click on users, select my user account, then click on security credentials.
3. next to assigned MFA device, we don't have any assigned devices. So, we are going to click on manage.
4. We're going to use a virtual MFA device. Now, for this, you will need an authenticator app installed on your mobile device or on your computer. I personally recommend the Google Authenticator app on my phone. So if you don't already have one installed, install the Google Authenticator app and then click on continue in your user screen.
5. The next thing to do is click show QR code. You'll need to point your phone's camera to the QR code, and it should open Google Authenticator. Once you've done that and you've got Google Authenticator open, it should be generating a code and displaying that on your screen.
6. Add the code that's on the phone screen right now to your MFA code one box on your webpage. And then you need to wait for that code to expire and it'll generate a new code and you need to add that into the MFA code two box and then click on assign MFA.

And that's it.

You've now got MFA enabled for your accounts, and you can see that we have an ARN for the virtual

### Set up for Root User Account 

See this webpage for directions [Click Here](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_enable_virtual.html#enable-virt-mfa-for-root)