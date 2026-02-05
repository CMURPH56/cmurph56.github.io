---
layout: single
author_profile: true
---


#### Why?

The backstory is I originally bought www.cammurphy.com from Google Domains. Then it was transferred to [Squarespace in 2023](https://www.theverge.com/2023/6/16/23763340/google-domains-sunset-sell-squarespace). At first I did not really mind because I was just sitting on the domain, but once I started using it again the features of Squarespace were not the best value for me. Squarespace seems more interested in being a domain registrar for people building and using the Squarespace service. I am more interested in building my own site and hosting it on GitHub Pages. What made more sense to me was using the [Cloudflare Registrar](https://www.cloudflare.com/products/registrar/), since I am already familiar with Cloudflare's other services.

#### Cloudflare Domain and DNS

The first thing I did was point DNS in Squarespace from GitHub directly to Cloudflare. This was so I could have everything flowing through Cloudflare before I started the transfer. I created the DNS record and had my Cloudflare account configured with the domain I was set to transfer. Cloudflare has a nice tool that will create proxied DNS records that point to where your DNS records were already pointing.

#### Transferring...

The next steps were updating the Name Servers in Squarespace to point to Cloudflare Name Servers, unlocking  the domain, and requesting the transfer codes. It took a while for those to be generated and sent over. After those steps were complete, I could complete the transfer.

####  Takeaways & Cloudflare Services

Both companies had great documentation and made the process pretty easy. I am also happy with the new free services I have access to in my Cloudflare account. For example: now I can get interesting insights into the traffic to my site. Apparently cammurphy.com is most popular in Ireland with 4k requests in the past 7 days. Well... more likely bots based in Ireland. 