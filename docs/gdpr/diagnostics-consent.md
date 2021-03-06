---
title: Handling User Consent
description: How to handle user consent with crashes and errors
keywords: GDPR, DSR, privacy, EU
author: blparr
ms.author: blparr
ms.date: 01/29/2019 
ms.topic: article 
ms.assetid: 26C66069-05D6-4EC2-84DD-AB86AF59EB97
ms.service: vs-appcenter
---

# Handling User Consent

## Ask for the Users' Consent To Send Diagnostics logs

If you want to get your users' confirmation before sending a crash/error report to App Center, the App Center SDK exposes a callback that instructs App Center Diagnostics to await confirmation from each user before sending any crash/error data to App Center.

You can read more about how to ask for the users' consent to send a crash/error log per platform:

- [Android Consent](~/sdk/crashes/android.md#ask-for-the-users-consent-to-send-a-crash-log)
- [iOS Consent](~/sdk/crashes/ios.md#ask-for-the-users-consent-to-send-a-crash-log)
- [macOS Consent](~/sdk/crashes/macos.md#ask-for-the-users-consent-to-send-a-crash-log)
- [UWP Consent](~/sdk/crashes/uwp.md#user-consent-to-send-a-crash-log)
- [React Native Consent](~/sdk/crashes/react-native.md#ask-for-the-users-consent-to-send-a-crash-log)
- [Xamarin Consent](~/sdk/crashes/xamarin.md#ask-for-the-users-consent-to-send-a-crash-log)
