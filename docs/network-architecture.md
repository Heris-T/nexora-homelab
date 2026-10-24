# Nexora Homelab — Network Setup

## How I Set Up My Homelab

I started Nexora as a personal project to explore self-hosted AI, Linux, networking, and automation.

Instead of running everything on my main computer or relying entirely on cloud services, I wanted a dedicated machine that could stay online and run different applications in the background.

I'm currently using a Dell laptop running Ubuntu Server as my homelab server. It connects to my home network through Ethernet.

The idea is simple: I want to be able to access Nexora from my computer, talk to my local AI assistant, and let it handle certain tasks automatically.

## How the Network Works

My setup is fairly straightforward.

**My computer → Home router → Ubuntu Server (Nexora)**

Nexora runs several services, including:

- **Open WebUI:** The interface I use to chat with Nexora.
- **Ollama:** Runs my AI model locally.
- **Market Research API:** Handles stock analysis and market research.
- **Risk API:** Evaluates trading setups and risk limits.
- **Flight Monitoring:** Checks flight information and prices.
- **Browser Automation:** Allows Nexora to perform supported browser tasks.

Open WebUI is accessible from my home network, while the internal Python APIs are configured to listen on localhost.

This allows the applications to communicate with one another without making every service directly accessible to other devices on the LAN.

## Docker Networking

One thing I've been learning through this project is how Docker networking works.

I'm currently using two networking approaches.

**Host networking**

Some of my Docker containers use host networking. This lets them share the Ubuntu host's network stack.

For my internal Python APIs, I've configured their services to listen on the loopback interface.

**Bridge networking**

My browser automation container uses Docker bridge networking, with its service port published only on localhost.

Working with these configurations has helped me better understand container networking, service bindings, and how applications communicate across different environments.

## Security

Security is something I want to build into Nexora from the beginning.

For example, I don't want to expose every application directly to the internet just because it's convenient.

I'm keeping API credentials separate from the application code, limiting direct access to internal services where possible, and reviewing what information can safely be shared.

I'm also being careful about what I publish on GitHub.

This repository won't include my actual IP addresses, passwords, API keys, authentication tokens, or private configurations.

There are still things I want to improve, especially reviewing the host firewall and verifying network access controls.

## Monitoring and Automation

Another part of Nexora I'm enjoying is making services work without needing me to manually start everything.

I've been using systemd services and timers to schedule tasks such as daily stock research.

I also integrated ntfy so Nexora can send notifications to my phone.

For example, after completing market research, Nexora can send me a short summary of the stocks it evaluated and the results.

It's a small feature, but seeing a self-hosted application perform a task and notify me automatically has been one of the more rewarding parts of the project.

## What I Want to Improve Next

There are several things I'd like to explore as the homelab grows:

- Better network and service monitoring
- Host firewall verification and hardening
- Network segmentation using VLANs
- Centralized logging
- Secure remote access
- More reliable backups and recovery
- Better documentation of the infrastructure

I don't want to make the environment unnecessarily complicated. My goal is to understand how everything works and improve it as I learn.

## Final Thoughts

Nexora is still a work in progress, but that's part of why I started it.

I'm using this project to gain more hands-on experience with Linux, Docker, networking, security, Python, and AI automation.

Some things work on the first attempt, others require troubleshooting, and sometimes I end up rebuilding parts of the system after learning a better approach.

That's what makes running a homelab interesting to me.

I'll continue documenting the setup, challenges, and improvements as the project develops.
