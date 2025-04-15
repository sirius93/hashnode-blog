---
title: "I built an AI Book recommendation App and was DDOSed for it."
seoTitle: "I built an AI Book recommendation App and was DDOSed for it."
seoDescription: "How I vibe coded my way into trouble and coded my way out of it..!!"
datePublished: Tue Apr 15 2025 10:37:13 GMT+0000 (Coordinated Universal Time)
cuid: cm9idbxgk000009l10cn48kah
slug: i-built-an-ai-book-recommendation-app-and-was-ddosed-for-it
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1744713215395/d734f5ba-48fe-43da-a994-8232425c0fac.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1744713408843/6c06c7b4-b29f-4b81-8c91-a464bd06614a.png
tags: cloudflare, ai, ddos, ddos-protection, vibe-coding

---

Last week, Google introduced its AI copilot Firebase Studio, and I decided to give it a try. It got me thinking about what I want to do next.

If you may be following me on socials, I just started a newsletter for book reviews & suggestions. Check [https://kitaaben.com](https://kitaaben.com). That got me thinking: What if I built a small book recommendation application that can help users get book recommendations based on their interests?

I started building it on Firebase studio. Started with a simple prompt to build an AI-based book recommendation application that shows a good variety of genres by default and an interest field for additional context. The Number of books you want to be recommended is either 1/3/6 or 12.

The initial version came with these fields. But after some iterations, I decided to add the email field and email integration to help users get the recommendation directly to their email.

The tech stack looks something like this:

* Nextjs + Reactjs ( For the application)
    
* Gemini API (For AI)
    
* Firebase (For Hosting)
    
* Resend (For Email - Free Tier)
    

The final version looked like this:

[![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744711016863/dd4268f4-7f57-4399-9fc3-83b724e4b07f.png align="center")](https://bookwise.kitaaben.com/)

After some testing and a lot of dopamine, I went ahead and made it public. Mapped it to a subdomain and made it public. Here is the URL if you want to give it a try: [https://bookwise.kitaaben.com](https://bookwise.kitaaben.com/)

I shared it in my friend’s WhatsApp group, Instagram, Twitter( now X), Linkedin almost everywhere I could.

But seems like someone didn’t like the spamming and decided to do something about it. By launching a DDOS attack on my website.Targeting my email functionality, trying to exhaust my email limit and increasing my cloud hosting + AI usage cost.

See the sudden spike in the requests?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744711671403/431a9532-9260-4fd6-9a0b-e89038891b24.png align="center")

Panic set in; I didn’t know what to do. Should I bring down the site and end this or something else? I decided not to give up and just think and act quickly

I did and quickly signed up for Cloudflare, added the Cloudflare protection layer to my app and observed the behaviour for some time. By this time, my email limit of 200 emails by resend had already been exhausted, so I waited for the next day and added a caching layer to store the emails and rate limit the emails to 3 emails per hour.

Things seem to be stable for now. The traffic has dropped as well. However, I would not mind some humans trying the app, benefiting from it and providing some real feedback.

If you are a human reading this, give the app a try. Tell me what you like/dislike. I am always just an email away at [connect@nandan.dev](mailto:connect@nandan.dev)

---

That’s all, folks! I hope you found this short note on Call, Apply & Bind helpful. If you enjoyed this, check out more articles on my website, [**https://nandan.dev/**](https://nandan.dev/)

Feel free to comment, email me at [**connect@nandan.dev**](http://mailto:connect@nandan.dev/), or connect with me on Twitter, Instagram, or GitHub. Don’t forget to subscribe to my newsletter for regular updates on JavaScript topics!

[**Twitter**](https://twitter.com/_sirius93_) | [**Instagram**](https://www.instagram.com/nandandotdev) | [**Github**](https://github.com/sirius93) | [**Website**](https://nandan.dev/)