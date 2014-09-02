---
layout: post
title: psexec - Error - Access is denied
---

Had a little problem today with our TeamCity build server not running the install step of our windows services using psexec.

The error displayed in TeamCity was "Access is denied".

![TeamCity Error]({{site.url}}/public/posts/2014-09-02-psexec-access-denied/TeamCityError.png)

After checking the following helpful articles and trying all the various fixes nothing was working:

* [StackOverflow - psexec Access Denied Errors](http://stackoverflow.com/questions/828432/psexec-access-denied-errors)
* [Sysinternals - Help](http://forum.sysinternals.com/topic15919.html)

Until one of my team mentioned that when he remoted onto the server the Sophos Antivirus was showing one quarantined file.

Sophos had quarantined "psexec.exe" and all that was needed was for me to authorise the exe in the antivirus control panel.

So just a gentle reminder to check the Antivirus before messing with the registry, secpol, folder permissions etc...