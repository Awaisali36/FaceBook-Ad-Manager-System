# 🚀 Facebook Ad Manager System

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![n8n](https://img.shields.io/badge/n8n-Automation-orange)](https://n8n.io/)
[![Airtable](https://img.shields.io/badge/Airtable-Database-blue)](https://airtable.com/)
[![AI Powered](https://img.shields.io/badge/AI-Powered-brightgreen)](https://github.com)

<div align="center">
  <a href="https://www.youtube.com/watch?v=Z_zoyLifS1s">
    <img src="https://img.youtube.com/vi/Z_zoyLifS1s/maxresdefault.jpg" alt="Facebook Ad Manager Demo" width="100%">
  </a>
  <p><em>Click to watch: Complete system walkthrough (5 minutes)</em></p>
</div>

> **End-to-end AI-powered automation system that transforms product information into production-ready Facebook ads in minutes.**

Replace entire marketing teams with an intelligent workflow that handles research, copywriting, creative prompts, and image generation automatically.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Tech Stack](#-tech-stack)
- [System Architecture](#-system-architecture)
- [Prerequisites](#-prerequisites)
- [Installation & Setup](#-installation--setup)
- [Usage Guide](#-usage-guide)
- [Demo Video](#-demo-video)
- [Workflow Breakdown](#-workflow-breakdown)
- [API Configuration](#-api-configuration)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)
- [Support](#-support)

---

## 🎯 Overview

**Facebook Ad Manager System** is a fully automated ad production pipeline designed for marketing agencies, e-commerce businesses, and small teams. Input your product details, and watch as AI handles everything from market research to final ad creatives.

### Who Is This For?

- 🏢 **Marketing Agencies** - Scale ad production without scaling headcount
- 🛍️ **E-commerce Businesses** - Launch campaigns faster with consistent quality
- 👥 **Small Teams** - Compete with enterprise-level creative output
- 💼 **All Business Types** - Adaptable to any industry or product category

### The Problem It Solves

Traditional ad creation requires:
- Market researchers to understand audiences
- Copywriters to craft compelling messages
- Art directors to create visual concepts
- Designers to produce final assets
- **Hours or days per ad set**

This system does it all in **minutes**, with consistent quality and unlimited variations.

---

## ✨ Key Features

### 🤖 **Complete Automation**
- Zero manual intervention from product input to final ad assets
- Intelligent workflow orchestration via n8n
- Automatic error handling and retry logic

### ⚡ **Time-Saving Powerhouse**
- Generate complete ad campaigns in under 10 minutes
- Produce 10+ image variations per ad copy
- Batch processing for multiple products simultaneously

### 👥 **Team Replacement**
- AI Market Researcher analyzes audience and pain points
- AI Copywriter creates headlines, body text, and CTAs
- AI Art Director generates detailed image prompts
- AI Image Generator produces professional visuals

### 🎨 **Multi-AI Integration**
- **Claude AI** for strategic thinking and copywriting
- **Gemini** for high-quality image generation
- **Perplexity** for real-time market research
- **OpenAI** for creative variations
- Intelligent model selection based on task requirements

### 📊 **Organized Workflow**
- Four structured Airtable interfaces for process management
- Version control for all generated content
- Centralized asset hosting via ImageKit
- Full audit trail of automation runs

---

## 🛠️ Tech Stack

| Category | Technology | Purpose |
|----------|------------|---------|
| **Database & UI** | Airtable | Product management, content storage, workflow triggers |
| **Automation** | n8n | Workflow orchestration, API integration, data processing |
| **AI Models** | Claude AI (Sonnet 4.5) | Market research, copywriting, prompt engineering |
| | Google Gemini | Image generation from prompts |
| | Perplexity AI | Real-time market intelligence |
| | OpenAI | Creative variations and fallback generation |
| **Image Hosting** | ImageKit | CDN-hosted image storage and delivery |
| **Integration** | Webhooks | Real-time triggers between Airtable and n8n |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        AIRTABLE INTERFACES                       │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  [1] Product Input → [2] Research Data → [3] Ad Copy → [4] Images│
│                                                                  │
└───────────────────────┬─────────────────────────────────────────┘
                        │ Webhooks
                        ↓
┌─────────────────────────────────────────────────────────────────┐
│                          N8N WORKFLOWS                           │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Flow 1: Research → Claude AI → Airtable Update                 │
│  Flow 2: Copywriting → Claude AI → Airtable Update              │
│  Flow 3: Prompt Gen → Claude AI → Batch Processing              │
│  Flow 4: Image Gen → Gemini → ImageKit → Airtable               │
│                                                                  │
└───────────────────────┬─────────────────────────────────────────┘
                        │
                        ↓
┌─────────────────────────────────────────────────────────────────┐
│                         AI SERVICES                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  • Claude AI (Research, Copy, Prompts)                          │
│  • Gemini (Image Generation)                                    │
│  • Perplexity (Market Data)                                     │
│  • OpenAI (Creative Variations)                                 │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## 📦 Prerequisites

Before installation, ensure you have:

### Required Accounts & API Keys

- ✅ **Airtable Account** - Base with appropriate permissions
- ✅ **n8n Instance** - Self-hosted or n8n Cloud
- ✅ **Claude AI API Key** - From Anthropic Console
- ✅ **Google Gemini API Key** - From Google AI Studio
- ✅ **Perplexity API Key** - From Perplexity Dashboard
- ✅ **OpenAI API Key** - From OpenAI Platform
- ✅ **ImageKit Account** - Public/Private keys configured

### Technical Requirements

- Node.js 16+ (for n8n self-hosted)
- Modern web browser
- Stable internet connection

---

## 🚀 Installation & Setup

### Step 1: Clone the Repository

```bash
git clone https://github.com/awaisali36/facebook-ad-manager.git
cd facebook-ad-manager
```

### Step 2: Airtable Setup

1. **Import the Base Template**
   - Navigate to `airtable-templates/` folder
   - copy `https://airtable.com/appiMP69otrP0K89q/shrdOO4CBi6FRHcLE`  base into your Airtable workspace
   
2. **Configure Four Interfaces**
   - **Interface 1**: Product Input Table
   - **Interface 2**: Research Data Table
   - **Interface 3**: Ad Copy Table
   - **Interface 4**: Image Assets Table

3. **Set Up Automations**
   - Create webhook triggers for each interface
   - Configure button fields to trigger n8n workflows
   - Link tables with proper relationships

### Step 3: n8n Configuration

1. **Import Workflows**
   ```bash
   # Import all 4 workflow JSON files from n8n-workflows/
   - flow-1-research.json
   - flow-2-adcopy.json
   - flow-3-prompts.json
   - flow-4-images.json
   ```

2. **Configure Credentials**
   - Add all API keys in n8n Settings → Credentials
   - Test each connection before activating workflows

3. **Update Webhook URLs**
   - Copy production webhook URLs from n8n
   - Update Airtable automation triggers with these URLs

### Step 5: Test the System

1. Open Airtable Interface 1
2. Add a test product (name + URL)
3. Click "Run and Create"
4. Monitor progress through all four interfaces
5. Verify final images appear in Interface 4

---

## 📖 Usage Guide

### Creating Your First Ad Campaign

#### 1️⃣ **Product Input** (Interface 1)

Navigate to the Product Input interface and enter:

- **Product Name**: "Ergonomic Office Chair Pro"
- **Product URL**: https://yourstore.com/office-chair
- Click **"Run and Create"** button

This triggers Flow 1 automatically.

#### 2️⃣ **Research Phase** (Interface 2)

The system automatically:
- Analyzes your product using Claude AI
- Identifies target audience segments
- Extracts key pain points
- Defines unique solutions
- Generates brand guidelines

**Output Example:**
```
Target Audience: Remote workers, 25-45, experiencing back pain
Pain Points: Poor posture, discomfort during long work sessions
Solutions: Ergonomic lumbar support, adjustable height, breathable mesh
```

#### 3️⃣ **Ad Copy Generation** (Interface 3)

Click **"Generate Ad Copy"** to produce:

- **Headline**: Attention-grabbing hook (40 chars max)
- **Primary Text**: Compelling body copy (125 chars)
- **Call-to-Action**: Action-driven button text

**Output Example:**
```
Headline: "Say Goodbye to Back Pain While Working"
Primary Text: "Our ErgoChair Pro supports your spine with medical-grade 
lumbar technology. Join 10,000+ pain-free remote workers today."
CTA: "Get 30% Off Now"
```

#### 4️⃣ **Image Prompt Creation** (Interface 3)

Click **"Generate Image Prompt"** to create 10 variations:

```
Prompt 1: Professional home office setup with ergonomic chair, 
side angle view, natural lighting, modern minimalist aesthetic...

Prompt 2: Close-up of chair's lumbar support mechanism, 
highlighting adjustable features, soft blue tones...

[...8 more variations]
```

#### 5️⃣ **Image Generation** (Interface 4)

Select desired prompts and click **"Generate Images"**:

- System calls Gemini API with each prompt
- Converts base64 responses to image files
- Uploads to ImageKit CDN
- Stores URLs in Airtable with metadata

**Result**: 10 production-ready ad images linked to your campaign!

---

## 🎬 Demo Video

### Watch the Full Walkthrough

<!-- Option 1: YouTube Embed -->
[![Facebook Ad Manager Demo](https://img.youtube.com/vi/YOUR_VIDEO_ID/maxresdefault.jpg)](https://www.youtube.com/watch?v=YOUR_VIDEO_ID)

<!-- Option 2: Direct Video Link -->
**[▶️ Watch Full Demo (5 mins)](https://your-video-link.com)**



---

## 🔄 Workflow Breakdown

### Flow 1: Research Data Collection

**Trigger**: Airtable button click → Webhook POST to n8n

**Process**:
1. Webhook receives product data
2. Claude AI assumes "Market Researcher" role
3. Generates structured brand guidelines
4. Updates Airtable with research results

**Duration**: ~30 seconds

---

### Flow 2: Ad Copy Generation

**Trigger**: "Generate Ad Copy" button → Webhook POST

**Process**:
1. Webhook receives research values
2. Claude AI assumes "Copywriter" role
3. Outputs headline, primary text, CTA
4. Updates Airtable with ad copy set

**Duration**: ~20 seconds

---

### Flow 3: Image Prompt Generation

**Trigger**: "Generate Image Prompt" button → Webhook POST

**Process**:
1. Webhook receives ad copy fields
2. Claude AI assumes "Art Director" role
3. Generates 10 diverse image prompts
4. Batch processes all variations
5. Updates Airtable with linked prompts

**Duration**: ~40 seconds

---

### Flow 4: Image Generation & Hosting

**Trigger**: "Generate Images" button → Webhook POST

**Process**:
1. Webhook receives selected prompts
2. HTTP Request to Gemini API
3. Returns base64 encoded image
4. Converts to actual image file
5. Uploads to ImageKit CDN
6. Creates Airtable record with URL

**Duration**: ~60 seconds per image

---

## 🔐 API Configuration

### Authentication Methods

#### Claude AI
```javascript
Headers: {
  "Authorization": "Bearer YOUR_CLAUDE_API_KEY",
  "Content-Type": "application/json"
}
```

#### Gemini
```javascript
Headers: {
  "Authorization": "Bearer YOUR_GEMINI_API_KEY"
}
```

#### ImageKit
```javascript
// Base64 encode your private key
const encoded = Buffer.from("YOUR_PRIVATE_KEY:").toString('base64');

Headers: {
  "Authorization": `Basic ${encoded}`
}
```

#### Airtable
```javascript
Headers: {
  "Authorization": "Bearer YOUR_AIRTABLE_TOKEN",
  "Content-Type": "application/json"
}
```

---

## 🐛 Troubleshooting

### Common Issues

#### Webhook Not Triggering

**Problem**: Button click doesn't start automation

**Solution**:
- Verify webhook URL is correct in Airtable
- Check n8n workflow is activated
- Test webhook with manual POST request
- Review Airtable automation execution history

#### API Rate Limits

**Problem**: Image generation fails after multiple requests

**Solution**:
- Implement exponential backoff in n8n
- Add delay nodes between batch requests
- Monitor API usage in provider dashboards
- Consider upgrading API tier

#### Image Upload Fails

**Problem**: ImageKit returns 401 Unauthorized

**Solution**:
- Verify private key is correctly Base64 encoded
- Check ImageKit account has sufficient storage
- Ensure URL endpoint matches your account
- Test credentials with ImageKit API playground

#### Claude Returns Malformed Data

**Problem**: Ad copy doesn't parse correctly

**Solution**:
- Review system prompt in n8n workflow
- Add JSON validation node after Claude
- Check for special characters in prompts
- Enable Claude's response schema validation

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### Reporting Bugs

1. Check existing issues first
2. Create detailed bug report with:
   - Steps to reproduce
   - Expected vs actual behavior
   - Screenshots/logs if applicable
   - Environment details

### Feature Requests

1. Open an issue with `[FEATURE]` prefix
2. Describe the use case clearly
3. Explain why it adds value
4. Consider implementation complexity

### Pull Requests

1. Fork the repository
2. Create feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open Pull Request with detailed description

### Development Setup

```bash
# Clone your fork
git clone https://github.com/yourusername/facebook-ad-manager.git

# Create development branch
git checkout -b dev/your-feature

# Install dependencies (if any)
npm install

# Make changes and test thoroughly
# Submit PR when ready
```

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### What This Means

✅ Commercial use allowed  
✅ Modification allowed  
✅ Distribution allowed  
✅ Private use allowed  

---

## 💬 Support

### Get Help

- 📧 **Email**: letsautomatewithawais@gmail.com
- 🐛 **Issues**: [GitHub Issues](https://github.com/yourusern/facebook-ad-manager/issues)



## 🌟 Acknowledgments

Built with incredible tools from:

- [Anthropic](https://anthropic.com) - Claude AI
- [Google](https://ai.google.dev) - Gemini
- [n8n](https://n8n.io) - Workflow automation
- [Airtable](https://airtable.com) - Database platform
- [ImageKit](https://imagekit.io) - Image CDN
- [Perplexity](https://perplexity.ai) - AI research
- [OpenAI](https://openai.com) - GPT models


**Made with ❤️ by Trilles AI**

⭐ Star this repo if it saved you time!

📢 Share with marketing teams who need this!

🔗 Fork and customize for your agency!
