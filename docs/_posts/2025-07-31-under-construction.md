---
layout: single
author_profile: true
---

I recently decided to switch the domain of my blog from www.cammurphy.com to blog.cammurphy.com with plans to use www.cammurphy.com as a portfolio/personal landing site.

### The Portfolio Site

The portfolio site will be a static HTML and CSS web page, with the goal of making it lightweight and simple. [Jekyll](https://jekyllrb.com/) has served me well for this blog, but downloading and managing Ruby has been a bit of a pain. The new portfolio site is hosted on [Cloudflare Pages](https://pages.cloudflare.com), which has an easy-to-use integration with GitHub for deployments.

### The Swap

It only required this [commit](https://github.com/CMURPH56/cmurph56.github.io/commit/54db54e31ad6f241d338d103a1bcc323b1d59e6f) and a small update to the [GitHub Pages](https://pages.github.com/) settings for my Jekyll site to work with the blog.cammurphy.com domain. After updating the blog CNAME record to point to the GitHub Pages repository, the domain swap was complete.

### The Mess Afterwards

Mission accomplished—the new domain for my blog is blog.cammurphy.com 🎉. However, that led to two issues. First, since I already had Google index www.cammurphy.com via the Google Search Console, there are going to be broken links. To mitigate this, I had to update Google Search Console to remove www.cammurphy.com from the listing and index blog.cammurphy.com. The next problem is that www.cammurphy.com is not pointing anywhere helpful—I have to actually build out the personal/portfolio site.

### Next Steps

The next steps are to build out www.cammurphy.com. The current plan is to build it with just HTML and CSS to keep it as low-maintenance as possible. However, I can see myself reaching for a framework to simplify the development process. I also want to build out other subdomains of the apex cammurphy.com with other projects. We'll see.