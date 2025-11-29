### Intro

Here is another free service from Cloudflare I decided to add to my site, because why not!



### Cloudflare Dashboard

1. Log into your [Cloudflare Account](https://dash.cloudflare.com/login)  
2. On the left nav go to *Application Security* -> *Turnstile*
3. Click *Add Widget*
4. Name your widget
5. Add the Hostnames you would like to cover
6. I chose Managed for Widget Mode
7. Opting out of pre-clearence for now. I might tackle this in a future blog post. However, cf_clearence cookie made an appearance in my [last blog post](https://blog.cammurphy.com/2025/11/16/adding-cookies-to-the-cookie-jar.html) makes a re-appearence. 
8. Click *Create Widget* 


### In The HTML

I am mostly following [Cloudflare Documentation](https://developers.cloudflare.com/turnstile/get-started/client-side-rendering/).

I ended up adding the following HTML to my [website](https://www.cammurphy.com/) and the blog you are reading now:

```HTML
      <div 
        class="cf-turnstile" 
        data-sitekey="<site-id>"  
        data-theme="light"
        data-size="normal"
        data-callback="onSuccess">
      </div>
```

This worked! However, it did not really fit with the styling for my website. So, I changed the widget mode option to invisible.


Now it keeps the flow of the site without the interruption of the visible widget. This is fine for my low traffic informational website.
