---
layout: post
title: iOS Certificates & Provisioning Profiles
date: '2013-10-15'
tags:
- ios
- xcode
- certificates
- provisioning profiles
- development objc
tumblr_url: http://milesmatthias.tumblr.com/post/64122889953/ios-certificates-provisioning-profiles
---
For a new iOS developer, they can be really confusing. You have an app that you simply want other people to be able to test on their device, and you get directed to the Apple developer portal with certificates, devices, and provisioning profiles. Before your body goes into shock, read the rest of this post for a simple explanation of it all.



The combination of certificates, devices, and provisioning profiles is Apple’s answer to some difficult questions:

Q: How do you guarantee the app you’re downloading hasn’t been modified by some hacker and it’s actually from the developer/company that it says it’s from?

A: Certificates. Ever learned about PGP encrypted email? That whole business where there’s a public key and a private key? That’s what’s going on here, except you’re abstracted from having to worry about that because of the Mac app “Keychain Access”. When you add a new certificate in the portal and follow the instructions to use “Keychain Access” to upload a certificate request, “Keychain Access” uses your private key to create a public key, which is then embedded into the certificate request that gets sent to Apple. Apple hands you back a certificate that you then put into your keychain (now you can download and add it through Xcode automatically).

(Update: it looks like you can have Xcode manage your certificates/”Signing identities” in preferences as well.)



Note that there are different certificates for different scenarios too. Developer certificates are used when you’re just getting any old app (app id: *) to work and you’re developing locally and on your development device that’s tethered to your computer. An AdHoc certificate is used when you want to allow a few testers to install your app on their device before the public AppStore release. AppStore and AdHoc certificates are tied to a specific app (app id), and they usually use an organization’s certificate, since the certificate is how Apple knows what to show on the “Developed By” line in the App Store listing.

Q: How can we allow a handful of testers to install the app on their phone and try it out before we release it to the whole world through the App Store?

A: Devices & Provisioning Profiles. Apple only allows its users to install apps through the App Store. But when you’re a developer and you want some people to try it out before it goes to the App Store, you need to use provisioning profiles and devices.

First, you get someone to give you their device UUID (universally unique identifier), which usually is done through a service like Testflight or HockeyApp where a person can sign up to be one of your testers and the service will automatically email you their UUID. In order to prevent you from circumventing the App Store, Apple restricts you to only adding 100 devices in a year to your iOS developer account.



Then you create a provisioning profile. Each provisioning profile incorporates a certificate in order to sign the app securely from a specific person/organization. Provisioning profiles also declare who is able to install the build of the app. In the case of an App Store provisioning profile, it’s saying that that build of the app can be installed by anyone as long as it’s downloaded through the App Store.



When you’re getting some testers on board, you’ll want to use an Ad Hoc provisioning profile (and certificate). In the “Edit” screen of the provisioning profile, you’ll be able to select any of the devices listed in “Devices” in your developer portal. Check the box next to the ones you want to include (Note: you can always check or uncheck more or less later).

Generate this profile, download it manually or through the Xcode preferences, select it when archiving your app, and then you’ll be able to upload that .ipa file to a service like Testflight for your testers to install.

Some more guiding images:

Having Xcode automatically download provisioning profiles and certificates for you:


Updating certificate (“Signing identity”) selected in the project’s build settings in Xcode:
