## How I "Hacked" an Airline Website to get back my luggage: A first-person insight to the story.

Around 3 months back, I tweeted a thread to a famous airline in India, pointing out some flaws in their data security, and asked them to make a few changes to their website.

If you google my name or search for "Techie who hacked an airline to retrieve his luggage" you will find many articles on the whole incident. 

Some of you have already read the article in one place or the other.  Each one of them has its version of the story. Some of them have even quoted my words and others have quoted my tweets in their article.

I have been thinking about writing this for quite some time now and today I have finally decided to go ahead with it. It's my story after all.

Let me first tell you my story and then I will list out my takeaways from the whole incident.


### The Incident:
I was traveling from my parent's home to Bangalore, and my bag got exchanged with another passenger. It was an honest mistake from both our ends as the bags were similar in appearance.

### The Exchange: 
At the airport, I and my wife were one of the last few people to get to the conveyer belt and by the time we reached, there our bag had already been picked up by our co-passenger and he left his luggage behind which looked similar to our bag; So we took the bag and left.

### The Realisation:
I realized the mess, only after I reached home. My wife pointed out that the bag seemed to be different from ours as we don’t use key-based locks in our bags. As soon as we realized it, I was freaking out. The fear of losing my important belongings and having an unknown person's bag in my possession kind of freaked me out.

### The Struggle :
Right after I entered my home, I started calling the airline. After multiple calls and navigating through their IVR and of course a lot of waiting, I was able to connect to one of their customer care agents. They asked me to check the co-passenger's bag and look for a tag that contains their PNR and last name. I found the tag and provided them with the details. They supposedly tried to connect me with the co-passenger, but all in vain. 

Once they couldn’t get any resolution on the issue. I asked the customer care team member to provide me with the co-passenger's contact number. They declined to provide me the contact details of the person citing **privacy and data protection**.

### The Wait :
After the call did not work, the agent assured me that they will call me back when they are able to reach my co-passenger.



**Fact 1:** In case of baggage loss/exchange, an airline can take up to 10 days and sometimes more than 10-20 days to track and ship your bag. 

**Fact 2:** The airline does not have any digitized record of all the lost baggage that is kept in their warehouse.


![friends-chandler-bing.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1661187732165/DB91jeKC9.gif align="center")

I waited for a long time and then, I went to sleep without any resolution to the issue, Hoping for a call in the morning.

### The Act:
After I did not get any call from the airline, even after waiting till 11 AM the morning. I decided to take matters into my own hands.

I started digging into the airline's website trying the co-passenger’s PNR in the hope to get an address or number by trying different methods like check-in, edit booking, and update contact, but no luck whatsoever.

After all the failed attempts, my dev instinct kicked in and I pressed the F12 button on my computer keyboard and opened the developer console on the website, and started the whole check-in flow with the network log record on.

There, in one of the network responses was the phone number and email ID of my co-passenger. 

And that my friends, I call my **Low Key Hacker Moment** 😂😂.


![breezy-hacker (1).gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1661191404001/SaHp8iI48.gif align="center")

### The Execution:
Now comes the final part.
After getting the phone number of my co-passenger, I was able to reach him with the phone number I got from the logs,  met with him at a center point, and got our bags swapped. 

![giphy.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1661191803409/hTZXacu3h.gif align="center")

It was a win-win day for me. I got my bag back with all my stuff intact. phew... Lucky me..!!

On the same evening, I wrote my infamous tweet, that made me the "Hacker" as you know me today. You can read the whole thread here - 

%[https://twitter.com/_sirius93_/status/1508423479594733568?s=20&t=LTRcAwhNo4kHDzRfBIOHvg]

### Q&As: 
Now that I have narrated the whole incident. There may be a few questions in your mind. I will now try to answer them one by one. Let's get going -

- **Did I really hack the Airline website?**

   Well..!! Technically no. I just used the data they were sending over in an API call. The data was accessible and wasn't encrypted. So it was easy as it can be.

- **Was there a security flaw in the website? **
   
  If I go by the airline representative's word, it should be termed as a data security flaw.  But the cyber security experts are divided over it because in the airline industry it's a common practice to use the combination of PNR and Last name as a passphrase. 

  They also share the passenger's address information in the API response, which I believe is a serious security issue.

- **Should Airlines update their data security terms ?**
   
  In my humble opinion, the airline industry should collectively work and come up with a protocol and do away with this age-old method of using a combination of PNR and last name as a passphrase which is quite literally written on a piece of paper and attached to a passenger's bag.

- **Did the airline in question take my feedback & fix their data issue ?**
   
  They actually did work on my feedback. *They disabled the developer console on their website, Fiddler still works*   😏

- **What can fellow travelers learn from this incident?**

  What fellow travelers can learn from this incident is that :
  1. Do not share your boarding pass photos or your PNR details on social media or in the public domain.
  2. Always use unique identifiers or add an [Airtag](https://amzn.to/3QNnlTN) for tracking in your luggage. 

- **What can fellow developers learn from my experience?**

  What fellow developers can learn from my experience is that Even the biggest problems can be solved, If we apply the presence of mind and break the bigger problems Into smaller problems.

I hope I have answered all your questions and if I have missed anything, drop a comment below or shoot me a mail at [contact@nandankumar.info](contact@nandankumar.info) and I will try to answer.

You can also visit my website to read some of the articles at [https://nandankumar.info/](https://nandankumar.info/)

Stay tuned & connect with me on my social media channels. Make sure to subscribe to my newsletter to get regular updates on my upcoming posts.

[Twitter](https://twitter.com/_sirius93_) | [Instagram](https://www.instagram.com/_sirius93_) | [Github](https://github.com/sirius93) | [Website](https://nandankumar.info)




