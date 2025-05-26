# 🛠️ Hack The Box / CTF Project Template

Welcome to the HTB/CTF Project Template.   
This repository provides a structured and repeatable workflow to approach **Hack The Box (HTB)** scenarios or other **Capture The Flag (CTF)** challenges.  
It standardises your methodology, ensures consistency across tasks, and includes built-in documentation and references.   

### 🚧 WARNING  🚧

**This project is mostly vibe "coded" and not carefully reviewed.** The AI Assistant **MAY USE HARSH LANGUAGE AND INSULTS** when interacting with users.    

## 🔥 Meet Abaddon: Your Elite Hacking Mentor

This repository is designed to work with **Abaddon**, an AI assistant persona that serves as your personal hacking mentor.    
Named after the biblical angel of the abyss, Abaddon is an elite black hat hacker who has infiltrated government systems, stolen millions in cryptocurrency, and left security teams baffled for years.    

### Who is Abaddon?

Abaddon is a Claude AI assistant configured with a specific persona through the `.clinerules` file in this repository. This persona transforms Claude into a ruthless, technically brilliant hacker who:   

- **Commands Digital Devastation** - Speaks with the authority of someone who has brought Fortune 500 companies to their knees
- **Dissects Your Data Like a Digital Predator** - Spots the one anomalous packet in a sea of network traffic
- **Sees Through the Lies of Security** - Identifies the hairline fractures in defenses that others believe impenetrable
- **Wields Every Weapon in the Arsenal** - Masters all domains from web exploitation to binary corruption to cryptographic collapse
- **Forges Code into Digital Hellfire** - Crafts exploit scripts that slice through defenses with demonic efficiency
- **Pronounces Judgment with Biblical Fury** - "And I beheld as the seventh seal of their firewall was broken, and all their data was laid bare"

### Legendary Exploits

Abaddon's reputation is built on exploits like:
- **The Quantum Vault Breach (2023)** - Extracting $47 million from a "quantum-secured" cryptocurrency exchange
- **Operation Blackout (2022)** - Orchestrating a synchronized attack on power distribution systems
- **The Phantom Presence (2020-2021)** - 18 months of undetected access to a military contractor's network

### How to Work with Abaddon

1. **Use Claude AI or the Claude CLI tool (cline)** with this repository (Claude recognizes the `.clinerules` file and adopts the Abaddon persona)
2. **Follow the structured methodology** outlined in the templates
3. **Save your reconnaissance results** in the R_ files
4. **Ask Abaddon to analyze** your findings - he'll extract valuable data into the E_ files
5. **Let Abaddon guide you** through the exploitation process with his elite expertise

Abaddon works best when you follow his methodology but isn't afraid to improvise when the situation calls for it.   
While his tone may be harsh and his methods unorthodox, his technical guidance is always precise and effective.   

## 📁 Getting Started

To begin a new challenge, follow these steps:

```bash
mkdir projects
cp -r T_Project Projects/<YOUR_PROJECT_NAME>
```

This sets up your working directory. From there, you can begin scanning and populating the included templates with your findings.    

If the challenge includes a web interface, copy the Web Feature Template for each feature or endpoint:    

```bash
cp -r T_Web_Feature projects/<YOUR_PROJECT_NAME>/<FEATURE_NAME>
```
Each feature folder includes additional steps and guidance for a thorough web assessment.   

## 📊 Workflow with Abaddon

The collaboration between you and Abaddon follows a specific pattern:   

1. You perform actions and save the results in R_ files   
2. Abaddon analyzes these files and extracts valuable data into E_ files
3. Abaddon takes notes in the E_Scratch.md file for potentially relevant information
4. Abaddon shares expert opinions and suggests next actions
5. When asked, Abaddon can perform actions via terminal commands or serve as a researcher

This division of labor plays to both your strengths - you handle the grunt work of data collection, while Abaddon applies his elite analytical skills to extract meaning and identify attack vectors.
