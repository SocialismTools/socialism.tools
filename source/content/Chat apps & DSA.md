---
publish: true
title: Chat apps & DSA
tags:
---

Most DSA members are talking to their comrades on multiple apps. Few people love the status quo, and every few years it's someone's turn to say hey: why don't we try to fix this problem? There's lots of open source options! How hard could it be, anyway? Without spoiling the surprise answer at the end, just know this is the third complete rewrite of this post in six years.

## State of the chat
There are dozens of chat apps to choose from for team collaboration. They’re all difficult to test out before fully committing, and like to spread critical features across price levels. DSA is in a weird sport for most companies because we have enterprise-level needs (self hosting, SSO, admin tools, advanced features) with ~none of the budget.

Chat apps have been an ongoing discussion at the NTC for as long as I've been a part of it. To give interested nerds a hand when this starts up, I made a comparison chart of all the major options, below. Before that though, some information much more important than features:

## "Can we get licenses for-" Nope.
Let's get the easy options crossed off the list first. We have ~80,000 members. Only a fraction of these are on the forum or their local Slack/Discord/chat server.  Paying for even this subset of users at $2 per month would be too expensive for us. Nobody prices below this; most don’t even price *close* to this. We therefore have to rely on free services or self-host.

## A specter is haunting FOSS
Self-hosting an open-source solution like Mattermost, Rocket Chat, Matrix/Element, or Zulip seems like an obvious solution. Open-source for DSA tends to fall apart quickly given a few technical requirements, however:
- We barely have the resources to self-host one server. We definitely do not have the resources to set up each chapter with a self-hosted solution, unless there is a cheap coordination tool that reduces this (like Gridpane for WordPress). We can afford cost-effective solutions to manage open-source projects that allow us to replace an expensive vendor or hacked-together solutions with something better (Gridpane, at a single yearly fee, is replacing dozens of individual servers; we pay for Open Slides a relatively small amount for hosting because it's complex to host and mission-critical)
- Users will be in more than one organization/server (National DSA, their local chapter, a working group) so the ability to switch between these quickly and easily (or, to have shared channels) is essential
- At some point, we will have SSO, and that will solve our "nobody can ever remember their logins" problem, so the app should support SSO. Trying to get the org onto a new platform will be a multi-year effort and we only want to do this once.

And finally, the biggest problem of all: DSA has members from a wide array of backgrounds, many without prior exposure to workplace collaboration technology *of any kind*. Usability is therefore critical. The most usable tool is one a member already knows how to use, and FOSS tools ~universally have worse usability (by a lot or a little - usually a lot) from their popular counterparts. Keep in mind that if you grew up using Discord or IRC, or had to learn how to use Slack/Teams on the job, you are familiar with a mode and style of communication many people have never used.

Chat apps aren't complicated like learning to use CAD software is complicated, but social interaction mediated by technology is never as simple as it sounds. Even major chat apps run by billion-dollar companies face usability issues, like notifications not showing up when they should, too many undesired notifications, and chats the user wants to access being lost in a sea of other chats. This is before you even think about more complicated use cases for organizers, like how to onboard new members, keep relevant information up to date, legal/privacy concerns, and so on.

The old versions of this post had detailed comparisons of the apps, but this is very hard to keep up to date. Thankfully, it can be summarized easily:

## two OK options for DSA, and the bad one
Zulip and Matrix are the two best FOSS chat apps for us. They have decent feature sets, with Zulip being more mature but unique (In, Zulip, threads are first-class citizens - almost like a stream of very short emails)., and Matrix being more secure and a better fit for how our org is structured (private by design, distributed, cross-server chat as a core goal) but still very buggy and difficult to run (complex, bare-bones mod tools, encrypted by default means messages can be easily lost forever).

Rocket Chat and Mattermost are often cited in these discussions but both lock too many features behind a paywall. Consumer-oriented apps like Signal aren't built for the needs of large groups. The one consumer app built for the public - Discord.  

Discord is very popular, especially with younger people and gamers. Some chapters have a Discord already set up. Discord is an app for public gaming communities and would be a pretty poor fit for DSA on features alone. The fact that it's owned by Microsoft (zero privacy) and undergoing increasingly aggressive monetization should rule it out for serious use. That said - until we choose one app to use and get people to use it, Discord is simple and popular - it's hard to beat that.

## All of the non-tech parts

There isn't one ideal app for DSA. I would be surprised if there was an org-wide push to move to one app simply because there is not one clearly obvious winner. This is a bigger problem than it might seem. 

One longstanding issue with digital tools in DSA (and frankly many other orgs) is adoption. In DSA, democracy is our first priority. Even if an app was perfect and we had perfectly behaved users, if they made up only 5% of our total membership, the app will have totally failed. Any new software project in DSA needs to have wide buy-in but chat might be the toughest tool to do this with because it will touch everyone in the org. I'm not sure this would be a good idea for us to even attempt until we have SSO.

Even if perfect chat software was delivered to us by a higher power, and the entire org unanimously decided we should use it, we would still have some serious challenges. As of Feb. 2025, DSA's national office is understaffed, particularly in the tech department, and we are in a slow-moving budget crisis. Setting up national infrastructure requires national dollars and (correctly!) national oversight. Members leave, or simply disengage with, DSA all the time. Everybody gets busy with life, things happen. The risk of the one person with capacity and skills to help leaving is a serious risk for any tech project in DSA. Staff members need to have the time and skills to ensure the app stays up, or pay someone to do that for us. Both options are expensive and we don't have the money. We have a significant amount of existing software services / processes / technical debt that will likely suck up any new capacity we do get when a Data & Tech manager is hired. 

So: not an easy challenge to overcome. It doesn't mean we never will. But, being a democratic org, someone needs to build a consensus that this is something our members should care about and prioritize a fix for, and so far, that hasn't quite happened.