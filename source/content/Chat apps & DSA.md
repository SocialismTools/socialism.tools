Most DSA members are talking to their comrades on multiple apps. Few people love the status quo, and every few years it's someone's turn to say hey: why don't we try to fix this problem? There's lots of open source options, how hard could it be? Without spoiling the surprise answer at the end, just know this is the third complete rewrite of this post in six years.

## State of the chat
There are dozens of chat apps to choose from for team collaboration. They’re all difficult to test out before fully committing, and like to spread critical features across price levels. DSA is in a weird sport for most companies because we have enterprise-level needs (self hosting, SSO, admin tools, advanced features) with ~none of the budget.

Chat apps have been an ongoing discussion at the NTC for as long as I've been a part of it. To give interested nerds a hand when this starts up, I made a comparison chart of all the major options, below. Before that though, some information much more important than features:

## "Can we get licenses for-" Nope
Let's get the easy options crossed off the list first. We have ~80,000 members. Only a fraction of these are on the forum or their local Slack/Discord/chat server.  Paying for even this subset of users at $2 per month would be too expensive for us. Nobody prices below this; most don’t even price *close* to this. We therefore have to rely on free services or self-host.

## A specter is haunting FOSS
Self-hosting an open-source solution like Mattermost, Rocket Chat, Matrix/Element, or Zulip seems like an obvious solution. Open-source for DSA tends to fall apart quickly given a few technical requirements, however:
- We barely have the resources to self-host one server. We definitely do not have the resources to set up each chapter with a self-hosted solution, unless there is a cheap coordination tool that reduces this (like Gridpane for WordPress). We can afford cost-effective solutions to manage open-source projects that allow us to replace an expensive vendor or hacked-together solutions with something better (Gridpane, at a single yearly fee, is replacing dozens of individual servers; we pay for Open Slides a relatively small amount for hosting because it's complex to host and mission-critical)
- Users will be in more than one organization/server (National DSA, their local chapter, a working group) so the ability to switch between these quickly and easily (or, to have shared channels) is essential
- At some point, we will have SSO, and that will solve our "nobody can ever remember their logins" problem

And finally, the biggest problem of all: DSA has members from a wide array of backgrounds, many without prior exposure to workplace collaboration technology *of any kind*. Usability is therefore critical. The most usable tool is one a member already knows how to use, and FOSS tools almost universally have worse usability (by a lot or a little - usually a lot) from their popular (and free) counterparts. Keep in mind that, especially if you grew up with Discord/IRC, you are used to a mode of communication some people have never used.

This chat only includes features you can get for free, or in the case of self-hosted applications, after self-hosting the app.