---
title: "Uptime Monitoring"
layout: single
author_profile: true
---

I set up monitoring on my site, blog.cammurphy.com. I have two requirements: one - make sure my site has good up-time and two - be aware when it is down. I do not want to check my blog and see it down. I would have no idea when it went down or if it was a solid or wavering down. I also want to know if it is down in Europe or Asia, something not readily available from my browser.  For this, I am using a service called [Pulsetic](https://pulsetic.com/). 

### Why Pulsetic?
I chose Pulsetic over a dozen or so freemium services found recommended in forums and blog posts. It meets my basic requirements with displaying percentage up-time and notification options when the site is down. It has few additional cool features and options. It also has a polished, professional, and intuitive user interface. 

### Pulsetic Setup
They provide several different monitoring "types": website, keyword, port and ping monitoring. I chose the generic website monitoring option. The check would happen every 5 minutes and would wait 10 seconds for the site to response. I chose to get notified of a down via email. I do not need a text or call for this. 

For additional options, I chose to include an SSL Cert check. I also asked it to check for the response text includes *Cam's Tech Blog*. I do not think that will change, and it will help see if my site is having issues rendering content. 

### Pulsetic Features
The dashboard has helpful at a glance information: graphed and average response time, percent up-time, and when the SSL certificate will expire (Cloudflare let's encrypt *should* auto-renew). 

There are some additional features that I currently do not have a need for yet, but I will keep in mind. They  provide heartbeat monitoring to make sure your background jobs, cron tasks, and scripts run on schedule. I do not have any scheduled tasks currently running, so it is not a need. 

They also provide the options for creating your own status page, that will indicate if your services are up or down. I do not need a status page for my blog, status.blog.cammurphy.com? It seems like overkill. Maybe if the blog gets big enough some day. 

There are other paid features, that I did not pay much mind too. However, I did add domain registration monitoring on cammurphy.com.  I do not think Cloudflare would miss notifying me about a potential registration lapse but a second check is nice. 

### Yeah... but does it work?
The feature list meets requirements.However, the service is worthless, if the product does not meet requirements. 

The test:
1. In the Cloudflare Dashboard  break DNS by setting the answer of the `blog` CNAME record to an empty target.
2. Refill coffee and wait for an email notifying you the site is down. 
3. If the email is received, repopulate the CNAME record target with the correct answer. 
4. Refill coffee and wait for email notifying it's back up. 
5. If email received, you can confirm that notifications act as expected. 
6. Confirm downtime represented in dashboard.

**How did Pulsetic do?**
The results were satisfactory. It took less than 5 minutes between me breaking DNS and receiving the email notifying me that it was down. It took me the same amount of time to receive the email that the site was back up. That is in the time range that Pulsetic advertises. The dashboard also correctly recorded the amount of downtime.

### Qualms or Areas of Improvements
This is not a sponsored post, and I do not want to be at risk of it sounding like it is one. One confusing part of the monitor setup process was deciding between Website Monitoring and Keyword Monitoring. Here are the descriptions of each:
* Website Monitoring -> Check if a website loads and *remains* reachable. 
* Keyword Monitoring -> Check if a website loads and *stays* reachable. 
That is the same description.  The Website Monitoring already has the option to check response text!! Just combine them and maybe add check for keywords as an option. One other small thing, it would be nice if there was a *select all* option for locations. 

### Conclusion
Pulsetic seems like a solid service, that I am excited to use. It is nice to have a service that will keep Cloudflare in check. I am interested to see some of the analytics over the next couple months. Does response time fluctuate? Will certain location have different results? Cloudflare is a pretty reliable service. How many down emails will I get this upcoming year? 