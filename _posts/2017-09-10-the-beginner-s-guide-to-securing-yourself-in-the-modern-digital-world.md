---
layout: post
title: How To Not Be the Slowest Gazelle on the Internet
---

Equifax. Ugh.

The [news dropped yesterday](http://www.slate.com/blogs/the_slatest/2017/09/07/equifax_hack_exposes_personal_data_of_143_million_americans.html) that Equifax, one of the three credit bureaus, got hacked and leaked 143 million customers information, including the Social Security numbers, driver’s license numbers, birth dates, addresses, and more. This is devastatingly bad. I wrote up this for some friends a few years ago, but never published it. Today, I decided to publish it.

So without any further adieu, here are 6 personal internet security steps you absolutely need to take.

## What you will find in this guide:

1.  The Checklist (all the suggestions, none of the explanation)
2.  Introduction
3.  The Philosophy
4.  Software That Will Help
    1.  Password Managers
    2.  2 Factor Authentication
    3.  VPN
5.  Protect Your Credit
6.  Security Questions
7.  Conclusion

### 1) The Checklist:

_If you don’t want to read anything, you just want to know what to install and what to do, here’s your list. If you want more information on any of these, read on…_

1.  Download [1Password](https://agilebits.com/onepassword/), [go through their tutorial](https://support.1password.com/getting-started/), then change at least your bank, credit card, and email passwords.
2.  Enable 2-Factor Authentication on [every site you use on this list](https://twofactorauth.org/).
3.  Install, and use, a VPN. [Encrypt.me](https://encrypt.me/) if you use an Apple/iOS/Android or Windows device.
4.  Install [HTTPS Everywhere](https://www.eff.org/Https-everywhere) in your browser ([Chrome](https://chrome.google.com/webstore/detail/https-everywhere/gcbommkclmclpchllfjekcdonpmejbdp?hl=en), [Firefox](https://addons.mozilla.org/en-us/firefox/addon/https-everywhere/)).
5.  Freeze your credit at all three credit bureaus: [Experian](https://www.experian.com/freeze/center.html), [TransUnion](http://www.transunion.com/personal-credit/credit-disputes/credit-freezes.page), and [Equifax](https://www.freeze.equifax.com/Freeze/jsp/SFF_PersonalIDInfo.jsp).
6.  Use randomized answers to “Challenge Questions” and store them in 1Password.
7.  Make up a fictional mother’s maiden name and use that from now on.

### 2) Introduction: Your Social Security Number Is Already On The Internet

Home Depot. Target. OPM. Anthem. Sony Playstation. JP Morgan Chase. Ashley Madison. Equifax.

Hardware. Retail. Government. Healthcare. Entertainment. Banking. Cheating on your spouse. Credit score.

56 million. 70 million. 22 million. 80 million. 77 million. 76 million. 37 million. 143 million.

That’s 561 million reasons to keep reading.

These are just 8 organizations that have had massive data breaches and compromises recently. The rammifications of each of these breaches is mind bogglingly bad. Social security numbers were leaked. Medical data. Credit card information. Usernames and passwords.

“Passwords?” You might think that's not as bad as social security numbers. But consider this scenario:

1.  You signed up for a fantasy football league website, and it gets hacked. The bad guys get your username, email address, and password.
2.  You use the same password for a lot of sites on the internet, including your email account.
3.  The bad guys now have access to your email. But you were smart - you at least have a unique password for your bank account!
4.  The bad guys go to your bank’s website, put in your email address, and click the “forgot password” button.
5.  The bank sends a password reset email to your email account, which they have access to.
6.  They click the link, reset the password to “Ch1naRocks,” then log in and transfer all your money out.

That’s bad. Real bad.

You’ve probably been told a thousand times to “use strong passwords” (but what does that mean!?), “use a different password for every site” (how am I supposed to remember all those passwords!?), and “change your passwords every few months” (how am I supposed to memorize all those new, strong passwords every few months!?).

So we don’t do it.

Maybe we have a different password for Facebook and our bank, but good security seems so hard. And complicated. There are acronyms like HTTPS, VPN, 2FA, weird words like phishing, and the more you try to learn about all this, the more confusing and overwhelming it all gets.

I am not a security expert, although I do work in the technology industry. After being personally affected by the OPM hack, I realized my own security practices weren’t enough. I needed to do more than what I was doing. And if _I_ needed to do more... then my family and my non-technical friends DEFINITELY needed to do more.

I spent days looking for a good comprehensive “beginner’s guide to modern digital security” and came up with nothing. Lots of very technical information. Lots of jargon-filled articles. If you knew what you were looking for, you could sometimes find something specific and relatively beginner friendly… but I never found anything comprehensive. And what beginner knows exactly what they need?

So I’m writing it. Welcome to The Beginner’s Guide to Securing Yourself in the Modern Digital World.

### 3) The Philosophy

If you are ever the target, if someone wants to get YOUR data specifically, you’re pretty much doomed. There’s nothing you can do to stop them. It’s depressing, but luckily it's also pretty rare. (If you are important enough to be this sort of target, you should probably stop reading this guide and go hire a professional.)

But that’s okay. Because the approach you should take to security is “to outrun the lion, you must only be faster than the slowest gazelle."

If you take even just the first steps toward securing yourself and your data, there’s a good chance the bad guys ignore you and go after people who left themselves wide open. You just won’t be worth it.

That’s the goal of this guide. If you want total security, then you need to become an expert. If you just want to live your life in peace knowing you’re more secure than the average Joe or Jane, this guide will get you there.

### 4) Software That Will Help

#### A) Password Manager:

A password manager is exactly what it sounds like. It’s a piece of software that manages all your passwords for you.

When you sign up for a website, your password manager generates a random strong password and saves it so you never have to remember it.

(Aside: A strong password could look like this: Ffhs$ao8y2IO@*f90a*!fs*na. It could also look like this: Correct horse battery staple. A strong password just means it’s random, it’s long, and it would take a computer a very, very, very long time to guess. While “Correct horse battery staple” is dictionary words, it’s a bunch of them in a random order, and it turns out to be VERY difficult for computers to guess.)

When you log back in to that site, you unlock your password manager by typing in a single Master Password, and it fills in the username and password information for you. The Master Password is saved on your computer, rather than on the internet, so no one can get to it. The [webcomic XKCD](https://xkcd.com/936/) has [some good advice](https://xkcd.com/936/) on creating a good master password.

Some people think this is dangerous, because it goes against conventional wisdom like “never write your password down” or “don’t store passwords on your computer.” But done correctly it’s not only very safe, it's one of the most powerful security tools that exist today.

It means you can have a strong, unique password on every single site on the Internet. If one website gets hacked, it limits the damage to just that website - it won’t compromise your accounts on any other site.

**Recommendation:** [**1Password**](https://agilebits.com/onepassword/)**.** There are Windows, Android, Mac and iPhone apps, which should cover all your major devices. 1Password is pretty universally accepted to be one of the best password managers out there. You need to sync your data between your devices (phone, computer) somehow, but they have several fantastic options in a [great tutorial for getting started here.](https://support.1password.com/getting-started/)

**Strategy:**

You have a lot of passwords. This seems like a daunting task. We can make it simpler though by breaking up the work by level of importance!

Once you’ve set up 1Password, do <u>Phase I</u> immediately, <u>Phase II</u> when you can, and <u>Phase III</u> during everyday use of the internet. As you’re logging into each of these accounts, generate a new password with 1Password and use it as the new password for that account.

1.  <u>Phase I (Do right away!)</u>: Money and authentication. Banks accounts, retirement accounts, credit cards, PayPal, email, and Facebook. (if someone gets access to your email, they get everything). These are the MOST critical accounts - where your money sits, and how you get money in and out. Email and Facebook are included here because if someone gets ahold of your those accounts, they can pretend to be you and gain access to other sites, too. Don’t forget sites like Mint or CreditKarma here!
2.  <u>Phase II (Do when you can)</u>: Big purchase sites (like Amazon), social media (Tumblr, Twitter), and other sites or software with information important to you. Anywhere where someone might be able to use a credit card on file for a big purchase, pretend to be you, or access any other sensitive information.
3.  <u>Phase III (Do during everyday use)</u>: This is everything else. All those random, miscellaneous websites you have to log in to. Don’t go after all these right away (unless you want to!). Just reset them as you use them. Every time you log into a new site (or go to a site with a password saved), take a minute and reset the password with a strong, unique password from 1Password’s generator. It’ll add 30 seconds, tops, to your visit, but after a week or so you’ll hit all the places you visit on a regular basis, and you’ll be much more secure.

#### B) Two-Factor Authentication (2FA)

There are three different factors, or ways, you can authenticate yourself on the internet. Something you know, something you are, or something you have. A password is an example of something you know. Fingerprints are something you are. Your cell phone is something you have.

One-Factor Authentication is what most of the internet uses: a username and password. These are things you know.

Two-Factor Authentication is where the internet is moving. Using a combination of something you know (username/password) with either something you are (fingerprints), or something you have (like a cell phone).

Two-Factor Authentication is, hands down, one of the best ways to further secure yourself online. Google, Apple, and Facebook all encourage their customers to use it.

It’s pretty simple, too. After you put in your password, a website will email or text you a one-time use secret code. You put that code into the website to confirm your identity, and then it lets you log in.

Even if someone steals your strong, unique password, they'd ALSO need access to your email or phone (which is hard to get), or your finger (which is hopefully even harder to get!).

Look through this list of sites that use [Two-Factor Authentication](https://twofactorauth.org/). If you use any of these companies, take a minute and enable it. Save time and do this as you’re changing all your passwords to put into 1Password.

#### C) Virtual Private Network:

These let you encrypt the communication between your laptop and “The Internet."

Have you ever been in a coffee shop and used their free Wi-Fi? Did you know that with a few simple pieces of software, anyone in the coffee shop could eavesdrop on everything coming through your internet connection?

That means they could digitally listen in when you put your password into Gmail, when you file your taxes, or when you’re collaborating with your coworkers on a sensitive business document.

The first step to stopping this from happening is to use a “Virtual Private Network.” In layman’s terms, this encrypts your internet connection between you and a computer out on the internet. People at the coffee shop can still listen in, but they’ll see something like “kh4UNyuKGM{G4.7” instead of “my password is ilovedogs123."

To learn more about VPNs, you can [watch this short video](https://www.youtube.com/watch?t=107&v=B41vCC4KLkY), “VPNs in Plain English."

**Recommendation:**

**OSX/iOS/Android/Windows:** [Encrypt.me](http://encrypt.me). The simplest VPN I’ve ever used. It’s beautiful and well designed, sits in the background, and will connect automatically when it detects an unsecured internet connection. One of my all time favorite pieces of software.

#### 5) Protect Your Credit

When a company leaks your credit card number, social security number, or other personal information, the standard response is to offer a year or two of free “credit monitoring services.” After the OPM hack, the federal government is offering all 22 million people effected three years of monitoring, at the cost of over $300 million dollars.

It’s great that organizations are taking responsibility and trying to help those affected, but monitoring services are just that - monitoring. If someone steals your identity and opens up a new credit card in your name, you still have to deal with the fallout, which can be terrifying, stressful, confusing, and expensive.

So what can you do?

Freeze your credit! This makes it temporarily impossible to open up a new line of credit in your name. (it does NOT stop your credit score from changing. Your credit SCORE can still change, this just prevents someone from getting your credit report or opening up a new line of credit)

I didn’t even know this was a thing you could do until recently, but in less than eight minutes (I timed it!), I froze my credit with all three credit bureaus ( [Experian](https://www.experian.com/freeze/center.html), [TransUnion](http://www.transunion.com/personal-credit/credit-disputes/credit-freezes.page), [Equifax](https://www.freeze.equifax.com/Freeze/jsp/SFF_PersonalIDInfo.jsp%0A)). Depending on what state you live in, it may cost $5-$10 per company. Your credit score is NOT damaged or penalized by freezing your credit. $15-$30 to freeze your credit is a small cost to pay for the safety and protection it provides.

When you freeze your account, you’ll either be given, or asked to generate, a secret PIN. [Generate a random number](http://numbergenerator.org/random-6-digit-number-generator) if you have to, then keep it in 1Password (there’s a section called “Secure Notes,” which is perfect for things like this).

Sometimes you will need to let people access your credit. For example, you need to take out a car loan, open a new credit card, or apply for a job that does a credit check. As you’re getting ready to do this, use the secret PIN to “thaw” your credit, then banks and credit card companies can request your information again.

You do need to freeze your credit with all three credit bureaus, but for a maximum of $30, this is the single best thing you can do to protect yourself and your identity.

To freeze your credit, go to the Credit Freeze pages for [Experian](https://www.experian.com/freeze/center.html), [TransUnion](http://www.transunion.com/personal-credit/credit-disputes/credit-freezes.page), and [Equifax](https://www.freeze.equifax.com/Freeze/jsp/SFF_PersonalIDInfo.jsp).

Learn more about freezing your credit at the [FTC](https://www.consumer.ftc.gov/articles/0497-credit-freeze-faqs#can) and [Lifehacker](http://twocents.lifehacker.com/keep-your-identity-secure-with-a-credit-freeze-or-fraud-1719680993).

### 6) Security Questions

_What is your mother’s maiden name?_ You can find that on a marriage certificate… which is a public record.

_What is the name of your first boy/girlfriend?_ If you’re younger than 25, there’s a decent chance this information is on Facebook.

_Where was your first job?_ LinkedIn ruins this one.

_What was your high school mascot?_ A combination of Facebook or LinkedIn plus a bit of googling wrecks this question.

Most security questions are terrible. The answers are either obvious, or can be found with a little bit of clever googling or facebooking.

So how do you fix this? You can have the most secure password and login system ever, but if someone can just reset your password because they figured out your favorite movie from your Facebook profile… you have a pretty big liability.

It’s easy. Just make up answers.

My dad gave me this idea - when someone asked him to provide his mother's maiden name for security reasons, he made one up. Now he only ever uses that. Much more secure than using the real one, which is easily discoverable.

I use 1Password, generate a new password, and use that. My answer to “What is your favorite movie?” might be "DTR@8n8B#B9hFd.” Then I leave a note in my 1Password profile for that account that says “Favorite movie: DTR@8n8B#B9hFd.” Mother’s maiden name? It’s not Bananaphone, but I could use that. If I ever have to reset my password, I glance in 1Password to check on the answer to my question.

### 7) Conclusion

The [hacking scenes from CSI](https://www.youtube.com/watch?v=u8qgehH3kEQ) are notoriously, painfully, hilariously bad. The real world doesn’t quite work like that. But personal internet security is an incredibly serious issue.

In 2012, there was over $24.7 billion in losses due to identity theft. Those are the latest statistics I could find, but I can only imagine that number is going up, not down.

There is way, way more you could do to be even more secure. But let’s be honest - most of us prefer convenience over security. This guide is the minimum you should do to maintain the highest level of security with the lowest amount of work.

All in all, following this guide from start to finish should take between sixty and ninety minutes (depending on how many passwords you have to change).

You could also do any individual item here (like freezing your credit, which takes less than eight minutes!) and you would be objectively better off than you are today.

Go through and implement the six low effort, high security steps in this guide. Then send this guide to your friends and your family. If you do the things here, let me know in the comments so I know people are using this! If you have questions, email me [zaccohn@gmail.com](http://zaccohn@gmail.com).

There are lions out there. And they’re hungry. Don’t be the slowest gazelle.
