+++
title = "Introduction"
description = "A bit about how I got into tech, and where the professional and hobby sides of that passion come from."
date = 2026-09-15
updated = 2026-09-15

[taxonomies]
tags = ["giuliano", "general"]
+++

I was born in 1983, in a small town in Brazil, about 20,000 people, no internet, and computers were something only rich families had.

What I did have, around age 12, was a Super Nintendo and a serious problem: I was almost never happy with how games played out. The gameplay,
 the endings, I kept thinking it could all be better, if only I could get in there and change it. An older friend told me the only way to do 
 that was to learn to program. So I did.

I enrolled in computer classes that same year. By 13 I was writing actual code, Clipper Summer 85, Visual Basic, languages that sound ancient 
now but were my first real doors into something bigger. I wasn't modding games yet, but programming had already hooked me on something else: I
 could build things, make tools, create something out of nothing. That was enough to keep going.

I kept at it through my teens, and around 1998-1999 I got my first job, at the first internet provider in my hometown. That's where things really
 opened up. Linux, servers, network configuration, real infrastructure work, at a time when the internet in Brazil still felt like the Wild West. 
 No Google yet, dot-com companies appearing out of nowhere, and me building websites and watching business opportunities materialize almost overnight.
 That's when I fell in love with the whole thing at once: programming, the internet, and the chaos of building something out of it.

That excitement about the internet's chaos turned into an actual career. I started as a web developer, mostly with PHP, working for internet 
providers until 2002 and then full time in PHP until 2005. At the same time, on my own, I started teaching myself Java, since I could feel it 
becoming the industry standard, and C, because I wanted to build my own MUD.

From 2005 to 2007 I had basically two jobs at once. Full time at a software house building PalmOS mobile applications, which was mobile development
before smartphones even existed. On the side, I worked as a consultant coaching teams on Java, at another software house and at universities around
São Paulo. I was already becoming a tech lead without really planning for it.

In 2007 I moved into a Scrum Master role for a year, turning a struggling, disengaged team at a university project into a high-performing one that
shipped a large Java plus SQL Server system in record time. It taught me as much about people as it did about process.

2009 is when the real shift happened. I moved into the financial markets industry, first at a market-data company working on high resilience, low 
latency streaming systems, then in 2010 to Deutsche Bank as a consultant, fully focused on enterprise Java. I stayed eight years, growing from a
mid-level developer into a solution architect running multi-region projects, coordinating vendors, and reporting to stakeholders spread across 
different time zones.

From there I chased the architect path more deliberately. Three years as an Enterprise Architect at B3, the Brazilian Stock Exchange, where I got my 
first real exposure to cloud architecture, building the exchange's first cloud-based financial system together with Microsoft consultants on Azure. 
Then a smaller company, a credit bureau, where the team was tiny and my decisions had a direct line to the client, including being on call and fixing 
things at 2am. That's where I really learned what an architectural shortcut costs you six months later.

That experience is what got me noticed by Adyen, a global payments company based in the Netherlands. I joined as an Observability Engineer, and most 
of my work is developing and maintaining Java libraries that use low level Java APIs to produce observability data. I have also worked on highly 
resilient telemetry pipelines that process around one million requests per second, using Kafka and Elasticsearch. More recently, I have been part of a 
project modernizing our telemetry stack with OpenTelemetry based libraries and components, running on Kubernetes. I moved to the Netherlands in 2022, 
and I am still there.

That C I picked up back then never really went away. In the 90s I was an avid MUD player and, although I eventually stopped playing when new games 
came along, I never lost the love for the code behind it. Since 2015 I have been a volunteer on a CircleMUD project, working as technical leader
for a group of five to seven people, including three developers and a few community managers and content creators. Even being a hobby for me, I 
treat it with real engineering practices, and that is part of why the game has been running for 20 years without pauses. Over time this meant real
engineering challenges too, like migrating the codebase from old C standards to C99, and later modernizing it further to compile under newer GCC
versions, fixing a good number of hidden bugs along the way. If you want the full story of the team and what we have built, I will have a dedicated 
page for it in the Projects section.


Running the server also gave me opportunities to build tools to automate our process. I am writing a deployment tool in Go to improve the testing and
deployment pipeline of our game. Considering the restricted resources on our game server, I could not find any tool that would fit in my use case, so
I am building it myself. A great opportunity to learn a new language with a practical project. 

Besides C, I also spent time learning OpenGL, Unity3D and Blender on the side, mostly for fun and to understand how 3D games actually work under the
 hood.

Looking back, these two sides of my career come from the same place. Professionally, I get to work with resilience, observability and complex systems,
 always with a strong focus on doing things right because real money and real companies depend on it. On the hobby side, I get the freedom to do 
 things without any deadline or client behind them, just to understand how something really works, from a compiler warning to a game server that has 
 been running for 20 years. Different contexts, but the same curiosity that got me started at 12 years old, trying to change the ending of a Super 
 Nintendo game.

This blog will mostly be about my personal projects and hobbies. Expect posts about game programming, C and Go experiments, and sometimes some other 
random thoughts. The idea is to document and share part of my learning journey, both to force myself to structure my process and to, maybe, make the 
journey useful to somebody else.
