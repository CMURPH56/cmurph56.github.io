I recently decided to switch the domain of my blog from www.cammurphy.com to blog.cammurphy.com with plans to use www.cammurphy.com as a portfolio / personal landing site.


### The Portfolio Site
The portfolio site will be a static HTML and CSS web page, with the goal of making it light weight and simple. I want limited dependencies that I have to update. I like the services that [Jekyll](https://jekyllrb.com/) provides, but downloading and managing Ruby has been a bit of pain. I decided to host the new portfolio site on [Cloudflare Pages](pages.cloudflare.com), which has an easy to use integration with GitHub for deployments. 


### The Swap
It only required this [commit](github.comCMURPH56/cmurph56.github.io/commit/54db54e31ad6f241d338d103a1bcc323b1d59e6f) and a small update to the [GitHub Pages](https://pages.github.com/) settings for my Jekyll site to work with the blogs.bakermckenzie.com domain. After updating the { blog } CNAME Record to point to the GitHub Pages repository, the domain swap was complete.

### The Mess Aftewards
Mission accomplished, the new domain for my blog is blog.cammurphy.com 🎉. However, that led to two issues. First, since I already had Google index wwww.cammurphy.com via the Google Search Console, there are going to be broken links. To mitigate this I had to update Google Search Console to remove www.cammurphy.com from the listing and index blog.cammurphy.com. The next problem is ww.cammurphy.com is not pointing anywhere helpful, I have to actually build out the personal / portfolio site.

### Next Steps
The next steps are to build out www.cammurphy.com. The current plan is to build it with just HTML and CSS to keep it as low maintenance as possible. However, I can see myself reaching for a framework to simplify the development process. I also want to build out other subdomains of the apex cammurphy.com with other projects. We will see.