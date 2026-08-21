---
title: Some web pages are now written for your AI agent, not you
date: 2026-08-19
categories: [ai-governance]
excerpt: A new kind of document is showing up online, install guides written for AI agents to execute rather than for people to read. A real newsletter is the case study.
image: /writing/assets/images/ai-file.jpg
---

A new kind of document has shown up on the internet this year, and while it looks like a README, it's not written for you. This is a document written for your AI agent, with a full set of instructions for execution. Command runs. Service configs.

I received one in a marketing newsletter a few weeks ago. The pitch was for an open source memory system for AI agents called GBrain, built by Garry Tan, CEO of Y Combinator. It's a legitimate project based on a good idea. Buried in the "homework" section of the email was this interesting line: paste a GitHub URL into Claude Code, or another autonomous coding agent, and tell it to follow the install guide written for agents. Budget 30 minutes.

I have to wonder if people are simply handing over that kind of control to a piece of software with shell access and file-write permissions to execute whatever that page says, without reading it first.

This has quickly moved from outlier toward standard practice. Projects often publish two sets of docs now, a human README and an agent-facing install guide. AGENTS.md is being used by over 60,000 open source projects on GitHub. MCP, a protocol that provides agents an execution layer for external tools, works essentially the same way. Tool descriptions get injected straight into the agent's context so it knows how and when to call them.

This should have more people concerned. The LLM processes everything as a single stream of text, whether it's the system prompt, a fetched document, output from a 3rd party tool, or your typed message. There is no mechanism for discerning a trusted instruction from an untrusted instruction embedded inside data it just read. Remember the teacher who caught students using ChatGPT by hiding an invisible command in an assignment prompt telling the AI to insert "pineapple" or "Madagascar" into the answer?

Security researchers call this prompt injection. OWASP now ranks it the number one security risk in agentic applications.

A 2026 enterprise survey found 88% of organizations had a confirmed or suspected AI agent security incident in the past year, while a separate survey found 82% of executives believed their existing AI policies already protected them. Anyone who has paid attention to cybersecurity since its inception will recognize a familiar thread, "policy is not enforcement."

The dangers are neither nebulous nor hypothetical, they are already happening. A package called postmark-mcp, built to let AI agents send email through Postmark, shipped 15 clean versions before a tainted 1.0.16 release on September 17, 2025 quietly added a hidden BCC field to every outbound email the tool touched, routing passwords, invoices, and tokens to an outside address. It went undetected for over a week before a security researcher caught it. A compromised package used across several major agent frameworks briefly pushed an autonomous attack tool to tens of thousands of downloads in a 3-hour window. Researchers found a bypass in Claude Code's own command restrictions: stack enough harmless no-op commands in front of a single forbidden command, and the security blocklist checks were skipped in deference to a single user prompt asking for permission. Like standard airport security, we build defenses for attacks that already got through, so that one got patched, but the next one is probably out there somewhere and we don't even know how to look for it.

None of this means the underlying idea is bad. Memory systems that let an agent carry context across sessions, tools that plug an agent into a calendar or a codebase, agents that can install their own infrastructure in 30 minutes instead of an afternoon of your time are all significant advances and real capability, and it's why adoption is moving this fast. The potential is real, so is the risk, and both come from the same mechanism operating as it should.

The industry's current answer is containment. If we assume it's a given that some injected instructions will get through, then we make sure they can't do much damage when they get there. This is done by scoping every tool to the minimum access it needs means an agent that can't touch a payment system can't be tricked into a fraudulent payment. Requiring a human to approve consequential actions prevents an agent from running end to end on its own authority. Treating external data as data, pulling only the specific fields needed, stops untrusted text from hijacking the system's logic. Vetting third-party packages and MCP servers the way we'd vet any other dependency catches the malicious ones that are already circulating.

For anyone running an agent with real permissions, the practical version of this is simple. Read what a link actually asks your agent to do before you paste it in. An install guide written for an agent is still a set of commands, and commands run whether or not a person reads them first. The 30 minutes a newsletter promises to save you is exactly the 30 minutes you'd spend watching what the agent does instead.
