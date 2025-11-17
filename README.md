# Voithos: AR Multimodal Intelligence System

[![Snapchat Spectacles](https://img.shields.io/badge/Spectacles-AR_Glasses-FFFC00?logo=snapchat&labelColor=000000)](https://spectacles.snap.dev)
[![Claude AI](https://img.shields.io/badge/Claude-AI_Coach-6E44FF)](https://www.anthropic.com/claude)
[![Tavily Search](https://img.shields.io/badge/Tavily-Web_Search-00D9FF)](https://tavily.com)
[![Groq Vision](https://img.shields.io/badge/Groq-Scene_Analysis-FF6B35)](https://groq.com)
[![Reka AI](https://img.shields.io/badge/Reka-Emotion_Detection-FF4785)](https://reka.ai)

> **Real-time conversation intelligence on AR glasses** — Your AI copilot for social interactions, powered by multimodal AI and instant web knowledge.

---

## 🎯 What is Voithos?

**Voithos** (Greek for "helper") is an AR conversation assistant built for Snap Spectacles that gives you **real-time social intelligence**. It listens to your conversations, analyzes your emotions and surroundings, and provides **ultra-concise, contextual suggestions** directly in your field of view.

Think of it as having a **conversation coach, fact-checker, and scene analyzer** working together in under 10 words at a time — optimized for the constraints of AR glasses.

---

## ✨ Key Features

### 🎤 **Real-Time Speech Processing**
- **Snapchat VoiceML**: Converts user speech to text in real-time
- Low-latency transcription for seamless conversation flow
- Continuous listening mode for natural interactions

### 😊 **Emotion-Aware AI**
- **Reka AI Vision**: Analyzes facial expressions and emotional state
- Detects happiness, confusion, curiosity, surprise, and more
- Provides context-aware conversation suggestions based on emotional tone

### 🧠 **Intelligent Conversation Coach**
- **Claude AI (Anthropic)**: Generates ultra-concise conversation suggestions
- Emotion + speech + scene context = personalized recommendations
- One-liner suggestions (<12 words) optimized for AR display

### 🌐 **Real-Time Web Search**
- **Tavily Search API**: Provides verified, factual information instantly
- Searches based on user's actual questions (not AI suggestions)
- Ultra-compact display: 60-char summaries + 3 sources max
- Advanced search depth for accurate, up-to-date information

### 🎬 **Visual Scene Analysis**
- **Groq API (Llama 4 Scout)**: Analyzes what the user is seeing
- Provides conversational descriptions of environment, people, objects
- Enhances Claude's suggestions with visual context
- 5-second analysis intervals for real-time awareness

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    SNAP SPECTACLES                      │
│                     (AR Display)                        │
└─────────────────────────────────────────────────────────┘
                            │
                ┌───────────┴───────────┐
                │                       │
        ┌───────▼──────┐        ┌──────▼──────┐
        │   CAMERA     │        │  MICROPHONE  │
        │   TEXTURE    │        │   (VoiceML)  │
        └───────┬──────┘        └──────┬───────┘
                │                       │
        ┌───────▼──────┐        ┌──────▼───────────┐
        │  Reka AI     │        │  Speech-to-Text  │
        │  (Emotion)   │        │   Transcription  │
        └───────┬──────┘        └──────┬───────────┘
                │                       │
                │       ┌───────────────┘
                │       │
        ┌───────▼───────▼──────┐
        │   Groq Vision API    │
        │  (Scene Analysis)    │
        └───────┬──────────────┘
                │
        ┌───────▼────────────────────────┐
        │      CLAUDE AI                 │
        │  (Conversation Suggestions)    │
        └───────┬────────────────────────┘
                │
        ┌───────▼────────────────────────┐
        │      TAVILY SEARCH             │
        │  (Factual Web Information)     │
        └───────┬────────────────────────┘
                │
        ┌───────▼────────────────────────┐
        │      AR TEXT DISPLAY           │
        │  (Ultra-Compact Output)        │
        └────────────────────────────────┘
```

---

## 🛠️ Technical Stack

| Component | Technology | Purpose |
|-----------|-----------|---------|
| **AR Platform** | Snap Spectacles + Lens Studio | AR glasses hardware and development environment |
| **Speech-to-Text** | Snapchat VoiceML API | Real-time speech transcription |
| **Emotion Detection** | Reka AI Vision API | Facial expression and emotion analysis |
| **Conversation AI** | Claude AI (Anthropic) | Contextual conversation suggestions |
| **Web Search** | Tavily Search API | Real-time factual information retrieval |
| **Scene Analysis** | Groq API (Llama 4 Scout) | Visual scene understanding |
| **Backend** | JavaScript (Lens Studio) | Asynchronous API integration and orchestration |

---

## 🚀 Getting Started

### Prerequisites
- **Snap Spectacles** (2024 or later)
- **Lens Studio** (v5.7.2 or later)
- **API Keys** (see [API_KEYS_SETUP.md](./API_KEYS_SETUP.md)):
  - Anthropic Claude API key
  - Tavily Search API key
  - Reka AI API key
  - Groq API key

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Krigupt/Voithos.git
   cd Voithos
   ```

2. **Set up API keys**:
   ```bash
   # Copy the example config
   cp config.example.js config.js
   
   # Edit config.js and add your API keys
   # (See API_KEYS_SETUP.md for detailed instructions)
   ```

3. **Open in Lens Studio**:
   - Open Lens Studio
   - Select "Open Project"
   - Navigate to the cloned `Voithos` directory
   - Open `AI_Decor_Assistant.esproj`

4. **Configure Script Components**:
   - In Lens Studio, select the **Scene** hierarchy
   - Locate the script components:
     - `ClaudeIntegration.js` - Add your Claude API key
     - `RekaEmotionAnalyzer.js` - Add your Reka API key
     - `TavilySuggestions.js` - Add your Tavily API key
     - `GroqSceneAnalyzer.js` - Add your Groq API key
   - Connect the required inputs (Camera Texture, Text components, etc.)

5. **Deploy to Spectacles**:
   - Connect your Snap Spectacles
   - Click "Push to Device" in Lens Studio
   - Wear your Spectacles and start talking!

---

## 📱 Usage

1. **Put on your Spectacles** and launch the Voithos lens
2. **Start talking** - VoiceML will transcribe your speech
3. **Watch the AR display**:
   - 🧠 **Claude suggestions** appear in real-time (top)
   - 🌐 **Tavily search results** show verified facts (bottom)
   - 😊 **Emotion detected** (console logs for debugging)
   - 🎬 **Scene analysis** (console logs for debugging)

### Example Interactions

**Scenario 1: Learning about a topic**
- **You say**: "What is a hackathon?"
- **Claude**: "It's a coding sprint - ask about their favorite one!"
- **Tavily**: 
  ```
  🌐 VERIFIED WEB RESULTS
  ━━━━━━━━━━━━━━━━━━━━
  
  💡 A hackathon is an event where people collaborate on software/hardware projects...
  
  📚 Sources:
  1. What is a Hackathon? - MLH
  2. Hackathon Definition - Wikipedia
  3. How Hackathons Work - Dev.to
  
  🌐 Real-time search
  ```

**Scenario 2: Social conversation**
- **You say**: "I'm nervous about this presentation"
- **Emotion**: Anxious
- **Claude**: "Deep breath - you've got this! What's it about?"
- **Scene**: "Person standing in front of a whiteboard with presentation slides"

---

## 🎯 Use Cases

- **🎤 Public Speaking**: Get conversation starters and confidence boosters
- **📚 Learning**: Instant factual information about any topic
- **💼 Networking**: Contextual icebreakers based on emotions and surroundings
- **🧠 Memory Aid**: Quick facts and information retrieval during conversations
- **🌍 Travel**: Understand new places and cultures in real-time
- **♿ Accessibility**: Assist users with social anxiety or communication challenges

---

## 🏆 Challenges We Overcame

### 1. **AR Display Constraints**
**Problem**: AR glasses have limited screen space and text readability
**Solution**: 
- Ultra-compact output (<12 words for Claude, <60 chars for Tavily)
- Sentence extraction and intelligent truncation
- Clear visual hierarchy with headers and emojis

### 2. **Multimodal Integration**
**Problem**: Synchronizing 5 different AI services (STT, Emotion, Claude, Tavily, Groq)
**Solution**:
- Asynchronous JavaScript promises
- Polling-based emotion/scene updates
- Event-driven speech transcription
- API bridging between scripts (`script.api`)

### 3. **Search Query Accuracy**
**Problem**: Claude's conversational suggestions made poor search queries
**Solution**:
- Extract user's original question from STT transcript
- Prioritize user query over Claude suggestions
- Auto-rewrite queries into factual questions ("What is X?")
- Use Tavily's advanced search depth

### 4. **Real-Time Performance**
**Problem**: Multiple API calls causing latency
**Solution**:
- Optimized polling intervals (5s for emotion/scene)
- Low-quality image compression for vision APIs
- Efficient Base64 encoding
- Claude's fast inference (<2s response time)

### 5. **Git LFS and Large Files**
**Problem**: 3D models, textures, and audio files caused Git push failures
**Solution**:
- Properly configured Git LFS for all binary file types
- Tracked `.glb`, `.gltf`, `.fbx`, `.hdr`, `.png`, `.jpg`, `.mesh`, `.wav`, `.mp3`
- Cleaned git history and pushed LFS objects separately

---

## 📊 Technical Highlights

- **Latency**: <3s end-to-end (speech → AI → display)
- **API Calls**: 5 concurrent services coordinated via JavaScript
- **Scene Updates**: Every 5 seconds for emotion and visual context
- **Search Accuracy**: Advanced Tavily search with 3 verified sources
- **Display Optimization**: Max 500 characters total for AR readability
- **Error Handling**: Comprehensive try-catch blocks with detailed logging

---

## 🔒 Security & Privacy

- **API Keys**: Never hardcoded - stored in `config.js` (gitignored)
- **Camera Access**: Only processed locally and sent to secure APIs
- **No Data Storage**: All processing is real-time with no persistent logs
- **User Control**: Can disable individual features (emotion, scene, search)

See [API_KEYS_SETUP.md](./API_KEYS_SETUP.md) for secure API key management.

---

## 📄 Project Structure

```
Voithos/
├── Assets/
│   ├── Scripts/
│   │   └── JS/
│   │       ├── ClaudeIntegration.js       # Main AI conversation coach
│   │       ├── RekaEmotionAnalyzer.js     # Facial emotion detection
│   │       ├── TavilySuggestions.js       # Web search integration
│   │       ├── GroqSceneAnalyzer.js       # Visual scene understanding
│   │       └── SnapchatSTT.js             # Speech-to-text
│   ├── 3D Models/                         # Boho, Scandi, Vintage assets
│   ├── Scene.scene                        # Main Lens Studio scene (gitignored)
│   └── ...
├── config.example.js                      # API key template
├── .gitignore                             # Excludes config.js, .env, Scene.scene
├── API_KEYS_SETUP.md                      # API key setup instructions
├── README.md                              # This file
└── ...
```

---

## 🎬 Demo Video

🎥 **Watch Voithos in Action**: [Coming Soon]

---

## 🤝 Contributing

We welcome contributions! Please see our contributing guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 🙏 Acknowledgments

- **Snap Inc.** - Spectacles platform and VoiceML API
- **Anthropic** - Claude AI for conversation intelligence
- **Tavily** - Real-time web search API
- **Groq** - Ultra-fast Llama 4 Scout inference
- **Reka AI** - Advanced emotion detection
- **Lens Studio Community** - Tutorials and support

---

## 📧 Contact

**Krishna Gupta**  
GitHub: [@Krigupt](https://github.com/Krigupt)  
Project: [Voithos](https://github.com/Krigupt/Voithos)

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Made with ❤️ for Snap Spectacles | Powered by 5 AI Models | Optimized for AR**
