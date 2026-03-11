# 🔗 LinkdAPI — OpenClaw Skill

> Give your OpenClaw AI agent full access to LinkedIn data — profiles, companies, jobs, posts, people search, and B2B lead intelligence.

---

## What This Skill Does

This skill connects your [OpenClaw](https://openclaw.ai) agent to the [LinkdAPI](https://linkdapi.com) REST API, unlocking **50+ LinkedIn endpoints** so your agent can research people, companies, jobs, and content on LinkedIn — in plain language, no code required.

Once installed, just ask your agent naturally. It handles the API calls, pagination, data enrichment, and synthesis for you.

---

## 💬 Example Questions You Can Ask

### 👤 Profile & Lead Research
- *"Look up John Smith at Salesforce on LinkedIn and give me his full work history and skills"*
- *"Find the LinkedIn profile for the CEO of OpenAI and get his contact info"*
- *"Get me the URN for username 'ryanroslansky' and then pull his recommendations"*
- *"Who are the top voices similar to this LinkedIn profile?"*

### 🏢 Company Intelligence
- *"Research Google on LinkedIn — give me headcount, recent posts, and open jobs"*
- *"Find all subsidiaries and affiliated pages of Microsoft on LinkedIn"*
- *"What companies are similar to Stripe on LinkedIn?"*
- *"Show me the last 10 posts from Anthropic's LinkedIn company page"*

### 🔍 People Search & ICP Targeting
- *"Find VP of Sales in San Francisco on LinkedIn who currently work at SaaS companies"*
- *"Search LinkedIn for marketing directors in London in the fintech industry"*
- *"Find people with the title 'Head of Growth' at Series B startups"*
- *"Search for Python engineers in Berlin open to remote work"*

### 💼 Job Market Intelligence
- *"What remote AI engineer jobs were posted on LinkedIn in the last week?"*
- *"Find all open marketing jobs at Shopify and get the hiring team for the top 3"*
- *"Search LinkedIn for junior developer jobs with easy apply and under 10 applicants"*
- *"What jobs has this LinkedIn profile posted recently?"*

### 📣 Content & Post Research
- *"Get the last 20 posts from this LinkedIn profile and summarize the themes"*
- *"Search LinkedIn posts about 'AI agents' from the past week sorted by latest"*
- *"Find all posts from Sequoia Capital on LinkedIn and pull engagement stats"*
- *"Get the comments on this LinkedIn post URN"*

### 📰 Articles & Thought Leadership
- *"Pull all LinkedIn articles written by this profile and summarize key insights"*
- *"Get details and reactions for this LinkedIn article URL"*

### 🎯 B2B Prospecting Workflows
- *"Build me a lead list: VPs of Marketing at SaaS companies in New York, include their LinkedIn profiles and current company"*
- *"Research this prospect before my call — LinkedIn overview, recent posts, and any articles they've written"*
- *"Find competitors of HubSpot on LinkedIn and pull their latest company posts"*
- *"Who is the hiring team for this job posting? I want to reach out directly"*

---

## 📁 File Structure

```
linkdapi-openclaw/
├── SKILL.md                  # Main skill — auth, endpoint map, workflows
└── references/
    ├── api-ref.md            # Full parameter schemas + response fields
    └── skills.json           # Machine-readable endpoint manifest
```

---

## 🚀 Installation

**1. Download** `linkdapi-openclaw.skill` from this repo

**2. Upload to your VPS**
```bash
rsync -avz -e "ssh -i ~/.ssh/your_key" linkdapi-openclaw.skill root@YOUR_VPS:/home/openclaw/
```

**3. Install on the server**
```bash
ssh -i ~/.ssh/your_key root@YOUR_VPS

mkdir -p /home/openclaw/.openclaw/skills
cd /home/openclaw/.openclaw/skills
unzip /home/openclaw/linkdapi-openclaw.skill
chown -R 1000:1000 /home/openclaw/.openclaw/skills/
```

**4. Add your LinkdAPI key** to `/home/openclaw/.openclaw/agents/main/agent/openclaw.json`:
```json
"skills": {
  "entries": {
    "linkdapi-openclaw": {
      "env": {
        "LINKDAPI_KEY": "your_linkdapi_key_here"
      }
    }
  }
}
```

**5. Restart OpenClaw**
```bash
cd /home/openclaw/openclaw && docker compose restart
```

Get your API key at **[linkdapi.com](https://linkdapi.com/?p=signup)** — 100 free credits included.

---

## 🔐 Authentication Note

The correct auth header is `X-linkdapi-apikey`. Do **not** use `x-api-key` or `Authorization: Bearer` — both will return 401.

---

## 📚 Resources

- [LinkdAPI Docs](https://linkdapi.com/docs)
- [OpenClaw](https://openclaw.ai)
- [Get a LinkdAPI Key](https://linkdapi.com/?p=signup)

---

*Built for OpenClaw. Powered by LinkdAPI.*
