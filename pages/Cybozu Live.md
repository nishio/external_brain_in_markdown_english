---
title: "Cybozu Live"
---

This is an interesting case study from a [[Technology Management]] point of view, in which a free service grows to 2 million users before it is terminated. (Note: The author was not involved in the Cybozu Live project at all, and this page is based on speculation and summary based on public information. The content of this page is not guaranteed, nor does it represent the opinion of the organization to which it belongs).

Brief description
- On November 26, 2009, the service was opened to the public in beta on an invitation-only basis.
- In August 2017, the total number of registered users exceeded 2 million.
- Announced on October 24, 2017 that services will end on April 15, 2019.

Published Facts
- November 26, 2009 - The service is opened to the public in beta on an invitation-only basis.
- October 25, 2010 - Officially open to the public with free registration
- December 14, 2010 [Hatena News PR article:](http://hatenanews.com/articles/201012/2098). Planning started in 2008, 4 team members, frameworks are Seasar and jQuery.
- July 19, 2011 - Cybozu releases "Cybozu Live for iPhone" iPhone application.
- December 7, 2011 Launch of Paid Services Postponed [Source:](https://archive.fo/cSHmJ) [Original URL:](https://magazine.cybozulive.com/2011/12/premiumplan.html)
    - > We are pleased to announce that the launch of "Cybozu Live Paid Option", which was scheduled to start in February 2012, has been postponed.
    - > Cybozu Live will continue to be available free of charge for up to 100 members per group until the paid option is launched.
    - *Following the launch of the paid option, the service will continue to be available free of charge for groups with 20 or fewer members.
- January 23, 2012 - Cybozu releases "Cybozu Live for Android" Android application.
- December 19, 2013 Expansion of Free User Limit to 300 users - Easier migration from "Yahoo!
- February 26, 2014 - Added features such as chat function, recycle bin function, login lock, CSV output of survey results, and emergency contact notification recipient settings.
- October 15, 2014 - Number of registered users exceeds 1 million
- In August 2017, the total number of registered users exceeded 2 million.
- On October 24, 2017, the company [announced](https://live.cybozu.co.jp/about/20171024.html) that its services will end on April 15, 2019.
    - > We have decided to terminate "Cybozu Live" against the backdrop of the need for investment, such as fundamental reworking, to continue stable service in the future due to the aging of the system, and the need for further investment in paid services.
    - CNET writes [https://japan.cnet.com/](https://japan.cnet.com/) that "the paid version groupware business is strong and further investment is essential to provide a comfortable service to subscribed users, and we have decided that we should focus on the paid version service considering our limited resources." article/35109275/]. The official source is [here](https://topics.cybozu.co.jp/news/2017/10/24-4407.html)

Common Reactions
- I'll pay you to continue.
    - [e.g.](https://twitter.com/tetsutalow/status/922724533206966277)
    - Published Fact: According to [IR [https://topics.cybozu.co.jp/news/2017/08/10-4218.html](https://topics.cybozu.co.jp/news/2017/08/10-4218.html) on August 10, 2017] sales are up 15% over last year and recurring profit has been revised down but is still expected to be in the black at 360 million.
    - It is not a matter of immediate cash.

Common Response 2
- I want it to be open source.
    - [Example](https://twitter.com/kur/status/922726300321583105)
    - A beta version was released in 2009.
    - According to a 2010 [Hatena News PR article](http://hatenanews.com/articles/201012/2098), the frameworks are Seasar and jQuery.
    - Apache + Tomcat + MySQL according to [lecture](https://www.slideshare.net/kazfuku/cybozulive-seleniumtest) in 2011
    - On September 26, 2016, many of the products offered by the Seasar project are End of Life (EOL) - [http://www.seasar.org/](http://www.seasar.org/)
        - This EOL was announced September 26, 2015 [Seasar Conference 2015](http://gihyo.jp/news/report/2015/10/2701)
    - > Attempted to break away from S2Dao with the EOL of Seasar, the Java framework used by Kintone and others.
        - [How did we make the wrong technology choice? 2016 - Cybozu Inside Out | Cybozu Engineer's Blog](http://blog.cybozu.io/entry/2016/12/28/101500)
    - Considering what "the system has become obsolete" and "investment such as drastic reworking is necessary to continue stable service," which are written as the reasons for termination in the release text, it would be difficult to provide the service even if the source code is made public.

Consideration of Nishio
- By announcing the end of the program after 18 months with 2 million registered users, a market of 2 million "Cybozu Live refugees" was created at this moment today.
- Customers discovered by free groupware are freed from lock-in.
- Since there is a year and a half until the end of the program and it will be exported to CSV, we should be able to acquire users efficiently if we add a function that allows migration.
- I have a feeling that various services will be created.
- And since users have experienced that "services hosted by one company will end unexpectedly," they should be concerned about the ease of transition.
- A Mastodon-like approach to Twitter will also emerge.
- A distributed communication infrastructure with a different timescale from Twitter and chat could be created.

- Is it still difficult for a for-profit company to continue to provide free services?
- Good up to the point where the project is launched and delivered, but threatened by dependent frameworks and other EOLs
- Is it impossible for software to continue to be used without being metabolized in the first place, not to mention a for-profit company?
- Does lock-in to services hinder metabolism?
- What should have been the role of groupware as "social infrastructure"?


Past Notices
Oct. 24, 2017 Notice of Termination of Cybozu Live Service
2017/08/02 [[8/13 (Sun.) from 1:00 AM]] Site maintenance (search function stopped)
2017/07/12 (Completed) [[7/12 (Wed.) from 15:00]] Site maintenance (several minutes down)
07/05/2017 Changes during site maintenance on Wednesday, 7/5 (no outage)
06/13/2017 Disabling TLS 1.0 encryption
06/12/2017 Changes for Site Maintenance on Wednesday, 6/14 (no outage)
2017/06/12 (Completed) [[Monday, June 12, noon-]] Site maintenance (stopped for a few seconds)
06/06/2017 (Completed) [[Saturday, June 10, from 22:00]] Site maintenance (60-minute outage)
2017/05/31 Beware of unrecognized email invitations!
2017/05/09 [[Sunday, 5/14, from 1:00 AM]] Site maintenance (30-minute outage)
2017/04/24 (Completed) [[4/27 (Thu.) from 15:00]] Site maintenance (search function: suspended for several minutes)
Apr 11, 2017 There is a delay in sending and receiving chat
Apr. 05, 2017 (Completed) [[4/9 (Sun.) from 1:00 AM]] Site maintenance (chat/timeline functions suspended)
Mar 28, 2017 (Fixed) Facebook login is not working (updated 3/30)
03/23/2017 (Repaired) Notification of current problems (added on 4/11)
03/15/2017 Notification of end of provision of old application for smartphones
2017/03/08 Notice of "Cybozu Live" IP address change (updated 6/6)
2017/03/06 (Completed) [[3/12 (Sun.) from 1:00 AM]] Site maintenance (1-hour suspension)
2017/02/03 (Completed) [[2/12 (Sun.) from 1:00 AM]] Site maintenance (1-hour suspension)
2017/01/23 (Completed) [[Tuesday, 1/24]] Site maintenance (non-stop)
12/21/2016 Smartphone-only application updated and consolidated into one.
2016/12/ 8 User Support during the New Year's Holidays
11/26/2016 (Resolved) Access problems (added 11/29/2016)
11/17/2016 Notice of current problems (added 11/29/2016)
11/15/2016 Changes during site maintenance on Tuesday, 11/15/2016 (no outage)
2016/11/7 [[Sunday, 11/13, from 1:00 AM]] Site maintenance (2-hour outage)
10/25/2016 (Completed) [[10/31 (Mon.) from 1:00 AM]] Cybozu Live Emergency Maintenance Notice
9/30/2016 An event is occurring in Mozilla Firefox that is preventing file attachments
9/9/2016 (Completed) [[9/11 (Sun.) from 1:00 AM]] Site maintenance (some service restrictions apply)
8/25/2016 Notification of current issues (added on 9/12)
8/10/2016 (Completed) Changes during Site Maintenance on Tuesday, 8/16 (Non-Stop)
8/8/2016 (Completed) [[8/14 (Sun.) from 1:00 AM]] Site maintenance (30-minute outage)
6/15/2016 (Completed) [[Monday, 6/20, 18:00-]] Site maintenance (non-stop)
6/6/2016 (Completed) [[6/12 (Sun.) from 1:00 AM]] Site maintenance (search/chat/timeline functions suspended)
5/19/2016 Update to "Cybozu Live TIMELINE"
5/17/2016 (Completed) [[Tuesday, 5/17/2016]] Emergency maintenance (non-stop)
4/28/2016 (Completed) [[Sunday, 5/8, from 1:00 AM]] Site maintenance (120-minute outage)
4/21/2016 (Completed) Changes during site maintenance on Monday, 4/25 (non-stop)
4/5/2016 (Completed) [[4/10 (Sun.) from 1:00 AM]] Site maintenance (60-minute outage)
3/23/2016 Update "Cybozu Live TIMELINE" - Support for QR Code and Invitation Link
3/14/2016 Added group invite/approval function by "QR Code/Invite Link".
3/9/2016 (Completed) [[3/13 (Sun.) from 1:00 AM]] Site maintenance (60-minute outage)
2016/2/10 (Completed) [[2/14 (Sun.) from 1:00 AM]] Site maintenance (search function stopped)
1/8/2016 Update of "Cybozu Live TIMELINE" for Android
1/6/2016 (Completed) [[Tuesday, 1/12, 18:00-]] Site maintenance (non-stop)
Call for participants for the user meeting to be held in Nagoya on Monday, 12/21/2015
12/15/2015 Download of New Cybozu Live TIMELINE App for Android Available
12/ 8/2015 (Completed) [[12/13 (Sun.) from 1:00 AM]] Site maintenance (search function stopped)
Dec 7, 2015 Update of "Cybozu Live TIMELINE" for iOS
2015/12/ 2 User Support during the New Year's Holidays
2015/12/ 2 (Completed) [[12/7 (Mon.) 18:00-]] Site maintenance (non-stop)
11/9/2015 (Completed) [[11/11 (Wed.) 18:00-]] Site maintenance (non-stop)
11/5/2015 (Completed) [[11/8 (Sun.) from 1:00 AM]] Site maintenance (20-minute outage)
November 4, 2015 New Timeline Feature and New Cybozu Live TIMELINE App for iOS Available for Download
11/2/2015 (Completed) [[11/4 (Wed.) 18:00-]] Site maintenance (non-stop)
10/29/2015 New app "Cybozu Live TIMELINE" coming soon
10/19/2015 Survey specifications were changed and functionality related to images was improved.
10/16/2015 (Completed) [[10/20 (Tue.) 18:00-]] Site maintenance (non-stop)
10/15/2015 (Completed) [[Thursday, 10/15, 18:00-]] Site maintenance (non-stop)
10/14/2015 (Postponed) [[10/14 (Wed.) 18:00-]] Site maintenance (non-stop)
10/6/2015 (Postponed) [[10/13 (Tue.) 18:00-]] Site maintenance (non-stop)
Oct. 2, 2015 (Completed) [[Oct. 11 (Sun.) from 1:00 AM]] Site maintenance (search function stopped)
9/7/2015 (Completed) [[9/13 (Sun.) from 1:00 AM]] Site maintenance (20-minute outage)
8/7/2015 (Completed) [[8/9 (Sun.) from 1:00 AM]] Site maintenance (30-minute outage)
2015/8/ 4 (Restored) [[8/4]] Emergency Maintenance
7/24/2015 (Completed) Notice of SSL Server Certificate Change
2015/7/13 (Completed) [[Tuesday, 7/14, 18:00-]] Site maintenance (non-stop)
7/6/2015 (Completed) [[7/12 (Sun.) from 1:00 AM]] Site maintenance (30-minute outage)
6/10/2015 (Completed) [[6/14 (Sun.) from 1:00 AM]] Site maintenance (tens of seconds)
6/1/2015 Functional improvements were made, including English display of chat
5/29/2015 (Completed) [[6/1 (Mon.) 13:00-]] Site maintenance (non-stop)
4/7/2015 (Completed) [[4/12 (Sun.) from 1:00 AM]] Site maintenance
4/2/2015 The first English-language version has been released!
3/31/2015 (Completed) [[Thursday, 4/2, 13:00-]] Site maintenance (non-stop)
3/30/2015 [[Restored]] Access problems (as of 3/30 10:00 p.m.)
2015/3/30 [[Restored]] Access failure due to increased load
2015/3/23 (Completed) [[3/30 (Mon.) 20:00-]] Site maintenance (non-stop)
2015/3/19[[Postponed]] Notice of SSL Server Certificate Change
3/3/2015 (Completed) [[3/8 (Sun.) 1:00 AM-]] Site maintenance (non-stop)
2/6/2015 (Resolved)2/6 Apology for access problem
2015/1/29 (Completed) [[2/8 (Sun.) 1:00 AM-]] Site Maintenance
1/22/2015 (Fixed) Google Calendar schedules may not sync using Cybozu Live Sync
1/13/2015 (Completed) [[1/14 (Wed.) 18:00- ]] Emergency maintenance (non-stop)
1/13/2015 Updates were made, including improvements to the display of the chat function
1/6/2015 (Completed) [[1/11 (Sun.) 1:00 AM-]] Site maintenance
2014/12/22 User Support during the New Year's Holidays
12/ 5/2014 (Completed) [[12/14 AM 1:00]] Notice of Site Maintenance
2014/12/ 1 Movie about working mothers' work styles released
11/18/2014 (Repaired) Unable to sync Google Calendar schedule using "Cybozu Live Sync".
November 4, 2014 Cybozu Live will not be available on some cell phones and Internet Explorer 6
10/15/2014 Number of registered users exceeded 1 million!
2014/9/26 (Completed) [[Thursday, 10/2, 6:00 PM to 7:00 PM]] Service display speed may be delayed
9/25/2014 (Repaired) Unable to create a survey using Internet Explorer.
9/16/2014 Updated functionality, including reuse of ToDo
8/5/2014 (Completed) [[8/8 (Fri.) from 1:00 AM]] Notice of Site Maintenance
2014/7/29 (Completed) [[8/5 AM 1:00]] Notice of Site Maintenance
2014/7/23 (Completed) [[Monday, 7/28, from 9:20 a.m. (20 minutes)]] Notice of Site Maintenance
2014/7/22 [[Restored]] Access failure due to increased load
7/17/2014 Apology for slow display speed
2014/7/10 (Completed) [[7/15 Early Morning 5:30am-]] Site Maintenance Notice
6/17/2014 (Completed) [[6/23 Midnight 24:00-]] Notice of Site Maintenance
2014/6/12 (Completed) [[6/17 AM 1:00]] Notice of Site Maintenance
2014/6/11 (Completed) [[6/13 AM 6:00]] Notice of Site Maintenance
4/21/2014 Status of Response to OpenSSL Vulnerability (Heartbleed Issue)
4/4/2014 [[4/7 AM 6:00]] Notice of Site Maintenance
2014/3/11 (Completed) Notice of Site Maintenance
2014/2/18 [[ 2/25 25:00 ]] Notice of Site Maintenance
2013/12/26 User Support during the New Year's Holidays
2013/12/24 Special Collaboration Calendar 2014 Present
2013/12/19 Expansion of free usage limit to 300 users - Easier migration from "Yahoo!
2013/12/6 Announcement of beta release of chat function
2013/12/ 5 [[completion]] Notice of Site Maintenance
2013/7/24 [[August 30]] Management Course for NPOs: "Let's Utilize it for Civic Activities! Cybozu Live
2013/5/16 [[ Completed ]] Notice of Site Maintenance
May 9, 2013 Number of registered users of Cybozu Live exceeds 500,000!
4/9/2013 Why not use Cybozu Live for your new activities this spring?
March 14, 2013 Seminar Information - "Cybozu Live Utilization Seminar" for NPOs [[ Monday, March 18, 2013 in Ichikawa City, Chiba Prefecture ]].
2013/3/ 6 Seminar Information - "Cybozu Live" Cloud-based Groupware Ideal for NPO Management
2013/3/ 1 The 50th Advertising Conference Awards "Cybozu Live Award" was announced.
2/18/2013 You can order a free brochure of Cybozu Live.
2012/12/26 Year-end and New Year business


Cybozu Live feature additions (to-do lists, file management, improved group events, etc.)
by @saicolobe on 2011/11/01Add this entry to Hatena BookmarksHatena Bookmark - Cybozu Live feature additions (to-do lists, file management, improved group events, etc.)
On November 1, 2011, Cybozu Live received a system update. This time, we have enhanced features such as To-Do lists, shared folders, and group events, greatly improving its usability as a project management tool.


---
This page is auto-translated from [/nishio/サイボウズLive](https://scrapbox.io/nishio/サイボウズLive) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.