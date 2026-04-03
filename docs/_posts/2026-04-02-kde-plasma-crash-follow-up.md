---
title: "KDE Plasma Crash Follow Up"
layout: single
author_profile: true
---

This post is following up on [my previous post about a KDE Plasmashell crash issue I was experiencing](https://blog.cammurphy.com/2025/12/14/kde-plasma-crash-investigation.html).  It has since been resolved, but not by any action I took. I am going to see if I can track down the change, commit, or release that fixed it. 

### Looking at Releases

When I first started noticing the issue, I was on version Plasma 6.5.4. When I realized for sure I was no longer seeing the issue, I was on Plasma 6.6.2. So there was one minor version, a major version, and two more minor version released. Also a side quest minor version on 6.5. 

- [Minor Release 6.5.4 - 6.5.5](https://kde.org/announcements/changelogs/plasma/6/6.5.4-6.5.5/)
- [Minor Release 6.5.6](https://kde.org/announcements/plasma/6/6.5.6/)
- [Major Release 6.5.5 - 6.6](https://kde.org/announcements/changelogs/plasma/6/6.5.5-6.6.0/)
- [Minor Release 6.6.0 - 6.6.1](https://kde.org/announcements/changelogs/plasma/6/6.6.0-6.6.1/)
- [Minor Release 6.6.1-6.6.2](https://kde.org/announcements/changelogs/plasma/6/6.6.1-6.6.2/)

There are a lot of changes in these releases. Particularly with the release of the major version 6.6. I will have to my search down to a few topics:
1. plasmashell   
	a. This is the product that was [crashing](https://blog.cammurphy.com/2025/12/14/kde-plasma-crash-investigation.html#first-section). Anything in the release notes that specified the term 'plasmashell' would be a good start. 
2. Terms like crash, fix, or bug  
	a. The changelog specifies bug fixes and new features. I want to filter out new features and focus on the bugs. 
3. KIconTheme KIconLoader  
	a. When I asked ChatGPT about the crash log this is what it singled out as causing the issue.

Searching through I realized this was going to be a long and maybe impossible task. There were many entries in the changelog and nothing I could find matched exactly what I was looking for. 

### A Better Way (KDE Bug Finder)

However! Combing through the changelog I found links to [the kde bug page](bugs.kde.org]) with a query parameter specifying the bugs unique id. This is a better way to find a resolved bug, because I could run a filtered search on the reported and resolved bugs. So, the search page was where I went. 

I used the advanced search page to narrow down my results. 

**Key Word Search:** 'Crash' (I initial had this set to 'Icon' but no results were found. I am not sure if this is because my exact crash log was not logged, or it was filed away as an attachment thus not found in keyword search.)  
**Classification:** 'Plasma'  
**Product:** 'plasmashell'  
**Component:** 'Generic Crash' (I guess... I could not find a specific component that matched my crash log)  
**Status:** 'Resolved / Closed' (I no longer experience the bug, so I figured it was fixed)  
**Resolution:** 'Fixed / Duplicate' ( I chose duplicate in case one was closer to my issue, but it was closed because it was also similar to another issue less similar to mine. )  

A list of bugs that seem very relevant to the ones I had were listed. I kept my search between January and March of 2026, because that is roughly when I started noticing it got better. 

![Image]({{site.baseurl}}/assets/images/kde_bug_list.png)

As you can see there is a lot of bugs *similar* to what I was experiencing during that time period. I could not find an exact match, but maybe different symptoms of the same disease. I narrowed the duplicates down to a few *root* bugs:  

https://bugs.kde.org/show_bug.cgi?id=511757  
https://bugs.kde.org/show_bug.cgi?id=514098  
https://bugs.kde.org/show_bug.cgi?id=506642  
https://bugs.kde.org/show_bug.cgi?id=500044  

Each had more than a few duplicate bugs tied to it.  I think https://bugs.kde.org/show_bug.cgi?id=511757 seems like the closest to the one I experienced. It also had the most duplicates tied to it. It says it was resolved in a special 6.5.6 release, which was released in March. However, I wonder if it was also fixed in 6.6 which was released in February. I am not sure how the release schedule works, maybe there is a release schedule for those who do not want to go to 6.6. So, for me I think the issue was finally fixed with the major 6.6 release in February.  

### Takeaways
Did I find the commit that fixed my issue? No. Do I want to spend any more time looking? No. Did I learn something about KDE Plasma's bug system and release schedule? Yes! Next time I run into a bug I will be able to log and check the status of it. This is a better approach than trying to figure it out on my own or hoping for a release to fix it soon. As always thanks to all the KDE Plasma contributors and maintainers. 

