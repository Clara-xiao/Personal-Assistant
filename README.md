# Earth Online daily newspaper system
Post daily tasks and the status of the day to your mailbox.
# 🎮 Earth Online Daily Report System

An AI-powered daily life gamification assistant that transforms your daily routine into an engaging RPG-style experience! Automatically sends personalized "gamified daily reports" to your inbox every morning.

## ✨ Features

- 🤖 **AI Content Generation**: Uses large language models to create engaging gamified daily reports
- 📅 **Calendar Integration**: Automatically reads today's schedule from Google Calendar
- 🌤️ **Weather Integration**: Fetches real-time weather data and provides outfit recommendations
- ⏰ **Automated Scheduling**: Sends reports automatically every morning
- 🎯 **Gamified Experience**: Transforms daily tasks into RPG-style quests and challenges

## 📧 Email Sample

```
🎮 [Earth Online Daily System Report]
🔔 Good morning, Player!

📅 Today's Quest Log:
┌──────────────────┬────────────────────┬──────────┬──────────────┐
│ ⏰ Quest Time     │ 📋 Quest Content   │ ⭐ Level │ 💎 EXP Reward │
├──────────────────┼────────────────────┼──────────┼──────────────┤
│ 09:00 - 10:00    │ Team Meeting       │ ★★☆     │ +50 EXP      │
│ 14:00 - 16:00    │ Project Dev        │ ★★★     │ +80 EXP      │
└──────────────────┴────────────────────┴──────────┴──────────────┘

🌤️ Today's Weather Instance:
┌─────────────────┬──────────────────────────┐
│ 🌍 Environment  │ 📊 Current Status        │
├─────────────────┼──────────────────────────┤
│ ☁️ Weather Mode │ Partly cloudy, good to go│
│ 🌡️ Temperature  │ 24°C                     │
│ 💧 Humidity     │ 65%                      │
└─────────────────┴──────────────────────────┘

🧥 Equipment Recommendations:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
• Upper: Light t-shirt or casual shirt
• Lower: Casual pants or jeans
• Accessories: Bring a light jacket as backup
• Reminder: Perfect temperature, no special gear needed
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📌 System Message:
🌟 Moderate quests today with pleasant weather. Have an amazing day! 🌟
```

## 🛠️ Technical Architecture

### System Components
- **n8n Workflow Platform**: Automation orchestration engine
- **AI Language Model**: Content generation (supports GPT/Claude etc.)
- **Google Calendar API**: Schedule data retrieval
- **Weather API**: Real-time weather information
- **Gmail API**: Email delivery service

### Data Flow
```
Schedule Trigger → Get Calendar → Get Weather → AI Generation → Send Email
```

## 🚀 Quick Start

### 1. Prerequisites
- n8n workflow platform (self-hosted or cloud)
- Google account (for Calendar and Gmail APIs)
- Weather API key (e.g., OpenWeatherMap)
- AI model API key (e.g., OpenAI, Anthropic)

### 2. API Configuration
```javascript
// Google Calendar API
scope: ['https://www.googleapis.com/auth/calendar.readonly']

// Gmail API  
scope: ['https://www.googleapis.com/auth/gmail.send']

// Weather API example
endpoint: 'https://api.openweathermap.org/data/2.5/weather'
```

### 3. n8n Workflow Setup

#### Node Configuration:
1. **Schedule Trigger**: Set daily trigger time
2. **Google Calendar**: Fetch today's events
3. **Weather API**: Get weather data
4. **AI Agent**: Generate gamified content
5. **Gmail**: Send email

#### AI Prompt Example:
```
You are an "Earth Online Game System" that generates daily gamified reports for players.

Input data:
- Google Calendar data: [schedule info]
- Weather API data: [weather info]

Output format: Gamified ASCII table daily report...
```

### 4. Email Configuration
```javascript
// Gmail node configuration
Message: {{ $('AI Agent').item.json.output }}
Subject: 🎮 Earth Online Daily Report - {{ new Date().toLocaleDateString() }}
Email Type: Text
```

## 📁 Project Structure

```
earth-online-daily/
├── workflows/
│   └── daily-report.json          # n8n workflow export
├── prompts/
│   └── ai-prompt-template.md      # AI prompt templates
├── docs/
│   ├── api-setup.md              # API configuration guide
│   └── deployment.md             # Deployment guide
└── README.md
```

## 🎯 Customization

### Personalization Options
- Modify gamification themes (sci-fi, fantasy, modern, etc.)
- Adjust sending time and frequency
- Customize email templates and styling
- Add more data sources (fitness, stocks, etc.)

### Extended Features
- Multi-channel support (WeChat/Slack/Discord)
- Task completion feedback system
- Integration with more life data (exercise, diet, etc.)
- Personalized learning and adaptation

## 🐛 Troubleshooting

**Q: AI generated content shows undefined?**  
A: Check data reference paths, ensure correct expressions like `{{ $('AI Agent').item.json.output }}`

**Q: Email format displays incorrectly?**  
A: Confirm Email Type is set to Text, HTML tables won't display properly in plain text mode

**Q: Schedule trigger not working?**  
A: Check timezone settings and ensure n8n service is running properly

## 🤝 Contributing

Issues and Pull Requests are welcome!

1. Fork the project
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

## 🙏 Acknowledgments

- [n8n](https://n8n.io/) - Powerful workflow automation platform
- [OpenAI](https://openai.com/) - AI content generation support
- [Google APIs](https://developers.google.com/) - Calendar and email services

---

⭐ If this project helps you, please give it a star!
