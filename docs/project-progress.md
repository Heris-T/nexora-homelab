# Nexora — Project Progress

## October 26, 2026 — AI Trading Research Agent V3

I've been making progress on Nexora, my self-hosted AI automation homelab.

My latest focus has been building an autonomous stock research agent that can discover opportunities, analyze information and send useful updates without requiring me to manually run every step.

### What I've built

- **Technical stock discovery:** Screens potential swing-trading opportunities.
- **Social momentum analysis:** Identifies stocks gaining attention in online communities.
- **News intelligence:** Collects news events and evaluates source and evidence quality.
- **Risk assessment:** Evaluates opportunities against predefined risk-management rules.
- **Automated reporting:** Combines research findings into structured daily reports.
- **Mobile notifications:** Integrates ntfy to send research summaries to my phone.
- **Linux automation:** Uses systemd to schedule unattended research.

### Testing and troubleshooting

The individual research and notification components have passed initial manual tests.

On October 26, I tested the first scheduled V3 execution. The service started automatically, but the workflow failed before completing the daily report and notification.

I'm investigating the failure and improving error handling before considering the automation production-ready.

### Safety

The project currently operates in research-only mode. Paper and live trade execution remain disabled.

### What's next

My priorities are fixing the unattended execution issue, strengthening data validation, improving stock selection, and making Nexora more reliable and autonomous.

This project is helping me develop practical experience with Linux, Docker, Python, AI integration, troubleshooting, automation and security-focused system design.
