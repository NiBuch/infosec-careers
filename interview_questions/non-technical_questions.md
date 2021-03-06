# Non-Technical Interview Questions
------
These are non-technical questions often asked in interviews to determine a candidate's familiarity 
with different information security communities, stances on industry topics, and "soft" skills. They're 
commonly used to assess a candidate's maturity, ambition, and how well they may fit into the team's or 
company's culture.

A resounding tip here is to stay level-headed when answering these questions. Recent graduates tend to bring 
extreme opinions to interviews thinking they'll look smart arguing them. In reality, it makes them look 
stupid and immature, and they often overstep in a way that costs them the job. You're there to impress with 
your skills and confidence, not to go on a diatribe about how you Macs are superior to Windows but you hate 
both because they're not open source.

------
### Terminology
------

+ **Explain the differences between a true positive, a false positive, a true negative, and a false negative.**

    In the context of security events, *True* means that our alerting device is reporting a condition correctly while
*False* means that the reported condition is incorrect. *Positive* means that our device is firing an alert, and
*Negative* means that the system is not alerting on any activity. Putting these together produces the following 
table:

    |           | **Positive** | **Negative** |
    |-----------|--------------|--------------|
    | **True**  | An event occurred and alerts were generated. | No event occurred and no alert was generated. |
    | **False** | No event occurred, but alerts were generated. | An event occurred, but no alert was generated. |

    **Note:** Sysadmins will often incorrectly say an alert is a false positive when their system is not 
vulnerable to a detected exploit. The true/false positive/negative conditions are based on whether the alert
was correctly generated, and not whether the alert was relevant. If the system was configured to alert
on the event, the event occurred, and an alert was generated, the condition would be a true positive.

------
### Industry Topics
------

+ **Where do you get your security news?**

    There are a huge number of places to get security news, but not all are created equal. Vendor blogs often 
have excellent write-ups for malware and emerging threats, while sources like [The Register](http://www.theregister.co.uk/security/), [The Hacker 
News](http://thehackernews.com/), and [Packet Storm Security](https://packetstormsecurity.com/news/) tend to 
cover new discoveries, major events, and "softer" news that doesn't get as technical. [The New York 
Times](http://www.nytimes.com/topic/subject/computer-security-cybersecurity), [Ars 
Technica](http://arstechnica.com/), and even [Forbes](http://www.forbes.com/security/) have security columns, 
and will sometimes do incredibly detailed reports for security events. Also good to mention here are any 
mailing lists you're on, and working groups you're a part of.  

    Poor answers are things like, "I check CNET" or "we get a news digest at work that I glance over." 
Virtually every player in security has days where some huge new threat pops up, and they need to understand 
it, explain it to their boss, and deal with it, usually all in the same morning it's disclosed. Someone who 
doesn't keep up with news usually won't be able to handle those situations when they happen.

    Mentioning hacking forums and groups here is a big 'it depends.' If you're in threat intelligence and you 
watch underground forums for new malware and threats, that's great. Saying you spend a lot of time on 
HackForums, however, is a good way to paint yourself as juvenile and not fit for professional security work. 

+ **What do you think is the biggest headline in security right now?**

    There's not really a right or wrong headline here, as long as you have one and it's current. If you can, 
try to spin it 
into a talking point: 

    + "That Example, LLC breach was pretty big. I got the dump, and have been doing some 
analyses on the password entropy."
    + "Definitely that CVE from last week. It's been pretty easy to exploit 
in my test environments, and it's gonna be hard to write a signature for."
    + "The new version of ExampleCrypt. I used to only see it delivered by malspam, but this week, I've started seeing it delivered by Angler." 

+ **Suppose you find a vulnerability in someone's website, application, etc. How do you go about getting it 
patched?**

    This is a test both of how you might handle something potentially damaging for the company, and your 
maturity. If it's a vulnerability you found as part of your work, the first step is always to check your 
organization's guidelines for reporting it to the client, and then report the issue to your supervisor. If 
you're informing the vendor/client, do so directly, through the best channels available. Work with the 
vendor/client as best you can, and be very careful who you tell about the exploit. This is critical, as 
mishandling that information could land you or your company in major legal trouble.

    What to do if the vendor/client does not cooperate in fixing the vulnerability is an opinion question. 
Some would say that making the vulnerability public forces the vendor's hand, while others would argue that 
disclosing it only gives malicious hackers more ammunition. One thing is for certain- there's a big 
difference between disclosing a vulnerability, and releasing a tool that lets any Joe Schmo exploit it 
automatically.

+ **Is open source software more or less secure than proprietary software?**

    A maturity question. The goal here is to list pros and cons rather than be biased towards one or the 
other. Yes, 'open source' can mean more eyes on it, but 'open source' can also mean that a 
professional developer, a college sophomore, and Russian Special Forces can all contribute to it, sometimes 
going unchecked. Proprietary software doesn't always get audited, but it often has better support, and 
there's a quality you get when the software is built entirely by professionals. Generally speaking, you can't 
tell a project's quality based solely on whether it's open or closed source.
