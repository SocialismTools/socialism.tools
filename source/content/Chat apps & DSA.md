---
publish: true
title: Chat apps & DSA
tags:
---
Most DSA members are talking to their comrades on multiple apps, which can be overwhelming to manage. Few people love this status quo, and every few years it's someone's turn to say "hey: why don't we try to fix this problem? There's lots of open source options! Let's try them out!" Without spoiling the surprise answer at the end, just know this is the third rewrite of this post in six years.
## State of the chat
There are dozens of chat apps to choose from for team collaboration. They’re all difficult to test out before fully committing, and like to spread critical features across price levels. DSA is in a weird sport for most companies because we have enterprise-level needs (self hosting, SSO, admin tools, advanced features) with ~none of the budget.

Chat apps have been an ongoing discussion at the NTC for as long as I've been a part of it. To give interested nerds a hand when this starts up, let's highlight some of the main challenges a project to centralize DSA's chat app would face.

## "Can we get licenses for-" Nope.
Let's get the easy options crossed off the list first. We have ~80,000 members. Only a fraction of these are on the forum or their local Slack/Discord/chat server.  Paying for even this subset of users at $2 per month would be too expensive for us. Nobody prices below this; most don’t even price *close* to this. We therefore have to rely on free services or self-host.

## A specter is haunting FOSS
Self-hosting an open-source solution like Mattermost, Rocket Chat, Matrix/Element, or Zulip seems like an obvious solution. Open-source for DSA tends to fall apart quickly given a few technical requirements, however:
- We barely have the resources to self-host one server. We definitely do not have the resources to set up each chapter with a self-hosted solution, unless there is a cheap coordination tool that reduces this (like Gridpane for WordPress). We can afford cost-effective solutions to manage open-source projects that allow us to replace an expensive vendor or hacked-together solutions with something better (Gridpane, at a single yearly fee, is replacing dozens of individual servers; we pay for Open Slides a relatively small amount for hosting because it's complex to host and mission-critical)
- Users will be in more than one organization/server (National DSA, their local chapter, a working group) so the ability to switch between these quickly and easily (or, to have shared channels) is essential. Most businesses don't operate like this, so federation is not implemented or bare-bones and enterprise-only if it is.
- At some point, we will have SSO, and that will solve our "nobody can ever remember their logins" problem, so the app should support SSO. Trying to get the org onto a new platform will be a multi-year effort and we only want to do this once.

And finally, the biggest problem of all: DSA has members from a wide array of backgrounds, many without prior exposure to workplace collaboration technology *of any kind*. Usability is therefore critical. If you grew up using Discord or IRC, or had to learn how to use Slack/Teams on the job, you are familiar with a mode and style of communication many people have never used. The most usable tool is one a member already knows how to use, and FOSS tools are nearly always harder to use than their commercial alternatives. This is a double whammy of usability that makes FOSS apps significantly more challenging to switch to.

Chat apps aren't complicated like learning to use CAD software is complicated, but social interaction mediated by technology is never as simple as it sounds. Even major chat apps run by billion-dollar companies face usability issues, like notifications not showing up when they should, too many undesired notifications, and chats the user wants to access being lost in a sea of other chats. This is before you even think about tech issues or more complicated use cases that organizers need.

The old versions of this post had detailed comparisons of the apps, but this is very hard to keep up to date. Thankfully, it can be summarized easily:

## two OK options for DSA, and the bad one
If we had to pick one today, Zulip and Matrix are the two best FOSS chat apps for us, largely though a process of elimination.
### Zulip
In, Zulip, threads are first-class citizens. Zulip channels are organized into "threads" that have a subject line, which helps keep multiple discussions in one channel separated. This is particularly useful at keeping old discussions relevant by simply adding a new message - something not really possible in any other chat app other than email. 
![[zulip.png]]
The downsides of Zulip is that mobile notifications and SSO [require a paid plan](https://zulip.com/plans/#self-hosted), even when self-hosting. Though it would likely be cheaper than any other product, even a few dollars per user per month is a financial hit, even with their non-profit discount. I would ordinarily write off Zulip for this, but they explicitly note they will offer special pricing to "Many organizations with special circumstances that make regular pricing unaffordable". The company building Zulip is [for-profit but got a lot of grant money and has never taken VC funding](https://zulip.com/values/#:~:text=We%20believe%20that%20the%20only,understand%2C%20operate%2C%20and%20modify.); they rely on their hosted product revenue to operate.
### Matrix
Matrix is a fully FOSS chat server software. Matrix's unique design is more secure and a better fit for how our org is structured. Conversations are private by design (so the server admin cannot see them) and cross-server chat as a core feature. Encrypted by default, however, means messages can be easily lost forever when users lose their password or secret (which they will, constantly). 

Being fully FOSS, Matrix actually many different pieces of software - you need to host the server and web client separately, in addition to a suite of other tools that handle login, S3 media offloading, bots, moderations tools, and so on. The official server solution is called Element Server Suite and cots 10EUR per user per month. There are 3rd party providers that make this much easier for less money though, like [Etke](https://etke.cc/order/), which offers Matrix, SSO, and other add-ons we would need for under $60 a month, with professional support only being another $100 a month extra. Matrix is technically a [UK-based nonprofit](https://matrix.org/foundation/about/) but the main server and client is built by the [for-profit Element company](https://element.io/blog/synapse-now-lives-at-github-com-element-hq-synapse/). Element is not yet profitable and their hiring page is empty.

### Everything else
Rocket Chat and Mattermost are often cited in these discussions but both lock too many features behind a paywall. Consumer-oriented apps like Signal aren't built for the needs of large groups. The one consumer app built for large group chats - Discord.  

Discord is very popular, especially with younger people and gamers. Some chapters have a Discord already set up, and Discord does have the ability to create "private" servers. However, Discord is an app for public gaming communities and would be a pretty poor fit for DSA on features alone (No SSO, few productivity integrations, terrible search). Discord is still privately held and is undergoing increasingly aggressive monetization which should rule it out for long-term use. That said - until we choose one app to use and get people to use it, Discord is simple, free and popular - it's hard to beat that.

## All of the non-tech parts

There isn't one ideal app for DSA. I would be surprised if there was an org-wide push to move to one app simply because there is not one clearly obvious winner. This is a bigger problem than it might seem. 

One longstanding issue with digital tools in DSA (and frankly many other orgs) is adoption. Democracy is our first priority. DSA is not a business where we can force people to use a new tool; we need to whip up support for it and get buy-in across the org. Even if an app was perfect and we had perfectly behaved users, if they made up only 5% of our total membership, the app will have totally failed. Any new software project in DSA needs to have wide buy-in but chat might be the toughest tool to do this with because it will touch everyone in the org. Chapters can be fiercely independent and may not want to turn over a core function of their daily operations to national, but I think that is an issue solved over time when early adopters become evangelists. 

Even if perfect chat software was delivered to us by a higher power, and the entire org unanimously decided we should use it, we would still have some serious challenges. As of Feb. 2025, DSA's national office is understaffed, particularly in the tech department, and while we were never rolling in money, we are now in a budget crunch. Setting up national infrastructure requires national dollars and national oversight. 
## why national oversight is good
Members leave, or simply disengage with, DSA all the time - everybody gets busy with life; things happen. The risk of the one person with capacity and skills to help leaving is a serious risk for any project in DSA - technical or not. Our members in staff positions act as the critical glue to ensure the organizing campaign keeps going or the app stays up. We have a significant amount of existing software services / processes / technical debt as-is and adding more on can be difficult. 

Given that we are member-run org, it's understandable to ask: why not have members take over more core functions? I think it would be great to have a more defined path for members to work on core tech in DSA, but we would need to do this democratically - decide what type of work (and permissions) we are OK with giving to volunteers (we do now know), what the change control process is (we do not have one), and all of the other work that goes into organizing labor. Many DSA systems, and even sending bulk email or texts in the wrong way, can get the org in serious legal trouble if managed poorly.

## Let a thousand threads bloom
So: not an easy challenge to overcome. It doesn't mean we never will. But, being a democratic org, someone needs to build a consensus that this is something our members should care about and prioritize a fix for, and so far, that hasn't happened.