+++
title = "Coding with AI: Episode 1 - Setting up the environment"
description = "Preparing my local environment for AI development. A fairly long, reflective post about installing Claude and Serena before writing any code."
date = 2026-10-05
authors = ["Giuliano Bortolassi"]

[taxonomies]
tags = ["giuliano", "general", "AI", "setup", "claude", "serena"]
+++

For quite a long time I have been working as a volunteer on the DeBo MUD project. It's a nice project, 
with, I would say, a noble goal, where I get to coach, and learn a lot from, a very nice group of people. 

But my selfish goal is to use the project to practice my coding skills in C and force myself to stay 
close to the actual code and solve low-level problems. That's no secret to the group. 

Still, this year, with coding agents going mainstream, my limited free time, and the desire to 
deliver new features for the game, I decided to try a different approach. I will start using 
AI to code for me. Not fully - yet - but as a tool to (hopefully) speed things up. So I subscribed
to a basic Claude plan and that's where this journey started. 


# My setup
I have a desktop PC. It dual-boots: Windows 11 with Ubuntu under WSL2, and a 'pure' Ubuntu install
running Wayland and Niri through DMS on a separate hard drive.
Usually, and by 'usually' I mean for at least the last seven years, Windows + WSL2 has been my setup 
for developing DeBo MUD.

For an IDE, I use CLion. I used to program using VS Code with C/C++ plugins, but that was not the greatest
experience, so I decided to pay for the JetBrains suite a couple of years ago and I am still using it, 
on both Windows and Linux. 


{{ responsive_image(src="photo_my_setup.jpg", alt="My Setup") }}


# Installing Claude

Ok, given my environment, I first installed Claude on Windows. I didn't give it much thought: just
as CLion on Windows can access my projects inside WSL2, I assumed Claude Code could do the same. 
It couldn't, at least not in a straightforward way, and since the whole point is to make up for my 
lack of time, I didn't want to spend it figuring that out. So, I installed Claude on WSL2, and it 
was smooth. 
   
Just run the 'super safe' installer (trusting it won't break your machine) and authenticate with
your Anthropic account. 

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

It was almost fine. I could run the Claude CLI/Harness inside WSL2 and use CLion to browse and review the
changes, but for some reason it was not great, and it was not a problem with Claude, or CLion, or Windows, 
or WSL2... it was the combination of all of them that didn't feel right. For instance, Claude Desktop, 
running natively on Windows, couldn't access the same files as the Claude CLI running in WSL2. For 
some weird reason my CLion integration with WSL2 started to lag, so editing code myself while the 
AI was working was sometimes unpleasant. Lazy mode on again, I decided to try running everything natively on Ubuntu.

That was it. It just works. IDE + Claude Code running on the same OS. Far fewer moving parts, as far as I 
can tell, and even with Claude Desktop being in beta, it works well with Wayland + Niri on Ubuntu. So far, 
zero problems. 

# Adding more tools

Once I had Claude and CLion working together, I noticed most of the AI's work was searching and reading
source files. Even though my current usage is not even close to my token limits, I wondered if that could be
improved. A colleague who is already a heavy user of Claude suggested adding an 
[MCP](https://en.wikipedia.org/wiki/Model_Context_Protocol) server that uses an [LSP](https://en.wikipedia.org/wiki/Language_Server_Protocol) 
to edit/query the code. Interesting idea, and that's how I got to know [Serena](https://github.com/oraios/serena). 
It's a nice concept, free and fairly easy to install.


### Installing Serena
As an Ubuntu/Debian user, I would expect the standard workflow: `sudo apt install serena`. Well, not this time,
which is understandable. MCPs are the new guys, and I think it might take a while before they become 
part of apt or any other official Linux package manager.  

The Quickstart section on the GitHub page shows what's needed, and it looks quite easy. 

`uv tool install -p 3.13 serena-agent` followed by a `serena init` command. Easy-peasy. Well, if you already
have `uv` installed. 

Installing `uv` is another 'leap of faith'. The command is simple: `curl -LsSf https://astral.sh/uv/install.sh | sh`
but how many times should I trust a random `.sh` script to run on my local machine directly from the web? On the [`uv` 
installation page](https://docs.astral.sh/uv/getting-started/installation/) they even say the installation script
may be inspected before use... it's only 2000 lines of shell script... seriously? 

I just ran it and prayed for things to go right. It went well... do I have backdoors on my machine now? Who knows.

With `uv` installed, installing and running Serena was a breeze. Configuring its integration with Claude was 
also quite straightforward. The Serena project offers good documentation, and that makes a big difference. I
even found a section dedicated specifically to [Serena with Claude Code](https://oraios.github.io/serena/02-usage/030_clients.html#claude-code).

The docs are more detailed, but it boils down to `serena setup claude-code`, and adding the MCP to Claude Code:

```bash
claude mcp add serena -- serena start-mcp-server --context claude-code --project "<path to your project folder>"
```

I chose to configure Serena+Claude on a per-project basis, as I don't see how useful it would be to have Serena on a non-code project, 
like documentation or even the repository I use to manage this blog.

The beauty of this Serena setup is that Claude starts and stops the Serena server with each session, 
and even shows a dashboard where you can monitor Serena usage, right out of the box. 

That was the basic setup, and with these two tools installed I started working on my first game feature using AI. But that's
for another post. 

(These are the three tools side by side)
{{ responsive_image(src="ss_setup_claude_serena_clion.png", alt="Final Setup") }}
