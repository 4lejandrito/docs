---
title: Top Sources
--- 

import useBaseUrl from '@docusaurus/useBaseUrl';

Your "**Top Sources**" report shows which referral sources are driving traffic to your website. You can use it to understand which marketing and promotional activities are working well and are driving traffic.

The referral sources are counted only when they start a new session on your site. This prevents external domains such as a payment gateway that the user is being taken through to show up in the referrers list. No need for you to manually exclude referrers.

<img alt="Top Referrers" src={useBaseUrl('img/top-referrers.png')} />

## How it works

There are two distinct ways that Plausible Analytics collects the referrer source for a visitor:

### 1. Automatic by the `referer` header

The `referer` header (the HTTP header is misspelled with one r for historical reasons) is the default and automated way of tracking referrer sources of web traffic. The `referer` header works well for the majority of cases but there are some limitations and fall-backs with using it for various historical and technical reasons. 

### Traffic without a referrer source

Not every request from a browser will have the referrer specified, and the `referer` header is not always accurate.

You may have noticed the "**Direct / None**" referrer source or you may be familiar with the term "**dark traffic**". This covers all the traffic where the referrer is not passed. These could be clicks from email, clicks from documents, clicks from messengers and other mobile apps, bookmarks, people typing in the URL directly into the browser and more.

Here’s a non-exhaustive list of other problems with the header:

* Whenever someone is moving from `http` to `https` or vice versa, the `referer` header is dropped.

* Facebook `referer` only includes the fact that the visitor came from Facebook. Facebook never sends the post or comment ID where someone clicked.

* Twitter sets the referrer to their link shortener (t.co) so you can see the shortened link but not the actual tweet that brought the traffic. [We make the best effort](twitter.md) to find the tweets that visitors came from using the Twitter API and display those tweets in your dashboard. Click on "**Twitter**" to view these.

* Google does not include the search keywords in the referrer so you can see that the visitor is coming from Google search but you cannot see which keyword phrase they used to find you. To fix this, you can [integrate your account](google-search-console-integration.md) with Google Search Console so the keyword phrases people discover your site with show in your Plausible Analytics dashboard. After integrating with Search Console, you can click on "**Google**" to view these.

Take a look at our blog post on the topic of [referrer header](https://plausible.io/blog/referrer-policy) for further details.

### 2. Manual by link tagging

To minimize the amount of traffic that falls within the "**nDirect / None**" category, you can add special query parameters to your links. 

See "[Manual link tagging](manual-link-tagging.md)" section of the documentation for the full instructions.
