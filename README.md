# AI Secretary App

## Overview
The AI Secretary App is an AI-powered personal secretary application designed to assist users with various tasks through voice and text interactions. It utilizes a local LLM (LLaMA 3 via Ollama) to provide intelligent responses and has memory-based context and retrieval-augmented generation (RAG) capabilities.

## Features
- Voice and text input support
- Intelligent responses using LLaMA 3
- Memory management for context-aware interactions
- User-friendly chat interface
- Settings management for user preferences

## Project Structure
```
ai-secretary-app
├── app
│   ├── src
│   │   ├── main
│   │   │   ├── kotlin
│   │   │   │   └── com
│   │   │   │       └── example
│   │   │   │           └── aisecretary
│   │   │   │               ├── MainActivity.kt
│   │   │   │               ├── SecretaryApplication.kt
│   │   │   │               ├── ui
│   │   │   │               │   ├── chat
│   │   │   │               │   │   ├── ChatFragment.kt
│   │   │   │               │   │   ├── ChatViewModel.kt
│   │   │   │               │   │   └── MessageAdapter.kt
│   │   │   │               │   └── settings
│   │   │   │               │       ├── SettingsFragment.kt
│   │   │   │               │       └── SettingsViewModel.kt
│   │   │   │               ├── data
│   │   │   │               │   ├── model
│   │   │   │               │   │   ├── Message.kt
│   │   │   │               │   │   └── ConversationContext.kt
│   │   │   │               │   ├── repository
│   │   │   │               │   │   ├── ChatRepository.kt
│   │   │   │               │   │   └── VoiceRepository.kt
│   │   │   │               │   └── local
│   │   │   │               │       ├── database
│   │   │   │               │       │   ├── AppDatabase.kt
│   │   │   │               │       │   └── dao
│   │   │   │               │       │       └── MessageDao.kt
│   │   │   │               │       └── preferences
│   │   │   │               │           └── UserPreferences.kt
│   │   │   │               ├── ai
│   │   │   │               │   ├── llm
│   │   │   │               │   │   ├── LlamaClient.kt
│   │   │   │               │   │   └── OllamaService.kt
│   │   │   │               │   ├── voice
│   │   │   │               │   │   ├── SpeechRecognizer.kt
│   │   │   │               │   │   └── TextToSpeech.kt
│   │   │   │               │   ├── memory
│   │   │   │               │   │   ├── ConversationMemory.kt
│   │   │   │               │   │   └── MemoryManager.kt
│   │   │   │               │   └── rag
│   │   │   │               │       ├── DocumentStore.kt
│   │   │   │               │       ├── Retriever.kt
│   │   │   │               │       └── VectorStore.kt
│   │   │   │               └── di
│   │   │   │                   └── AppModule.kt
│   │   │   ├── res
│   │   │   │   ├── layout
│   │   │   │   │   ├── activity_main.xml
│   │   │   │   │   ├── fragment_chat.xml
│   │   │   │   │   └── fragment_settings.xml
│   │   │   │   ├── values
│   │   │   │   │   ├── colors.xml
│   │   │   │   │   ├── strings.xml
│   │   │   │   │   └── themes.xml
│   │   │   │   └── navigation
│   │   │   │       └── nav_graph.xml
│   │   │   └── AndroidManifest.xml
│   │   └── test
│   │       └── kotlin
│   │           └── com
│   │               └── example
│   │                   └── aisecretary
│   │                       └── LlmClientTest.kt
│   └── build.gradle.kts
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

## Setup Instructions
1. Clone the repository:
   ```
   git clone https://github.com/A-Akhil/Astra-Ai.git
   ```
2. Open the project in your preferred IDE.
3. Copy `secrets.properties.template` to `secrets.properties` and configure:
   ```properties
   OLLAMA_BASE_URL=https://your-ollama-server-url
   LLAMA_MODEL_NAME=llama3:8b
   ```
4. Ensure you have the necessary SDKs and dependencies installed.
5. Build and run the application on an Android device or emulator.
6. Structured Logging

A new centralized logging utility has been added at utils/Logger.kt.

*Features:*
- Log levels: DEBUG, INFO, WARN, ERROR
- JSON-formatted logs with timestamps and component names
- File-based logging with rotation (5 files, 1MB each)
- Supports log level filtering and component tagging
- Logger initialized in MyApplication.kt

Useful for debugging and tracking issues in development and production.

### Model Configuration
The LLM model is configurable in `secrets.properties`. For low-RAM systems, use lightweight alternatives:

```properties
# Lightweight options (requires less RAM):
LLAMA_MODEL_NAME=phi3           
LLAMA_MODEL_NAME=llama3.2:1b    
LLAMA_MODEL_NAME=qwen2.5:0.5b   
LLAMA_MODEL_NAME=gemma2:2b      
LLAMA_MODEL_NAME=llama3:8b
```

## Usage
- Launch the application and interact with the AI Secretary using voice or text.
- Access settings to customize your preferences.
- The app will remember previous interactions to provide context-aware responses.

## Contributing
Contributions are welcome! Please submit a pull request or open an issue for any enhancements or bug fixes.

[![Contributors](https://contrib.rocks/image?repo=A-Akhil/CertiMaster)](https://github.com/A-Akhil/CertiMaster/graphs/contributors)

## License
This project is licensed under the MIT License. See the LICENSE file for details.

<div align="center">

## Please support the development by donating.

[![BuyMeACoffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/aakhil)

</div>

## Current Features ✅

<details>
<summary>🤖 AI & Machine Learning</summary>

- **LLM Integration**
  - [x] LLaMA 3 integration via Ollama
  - [x] System prompt management
  - [x] Context-aware responses
  - [x] Error handling and retry logic

- **Memory System**
  - [x] Basic memory storage
  - [x] Memory detection from responses
  - [x] JSON memory extraction
  - [x] Memory cleanup

- **Voice Processing**
  - [x] Text-to-Speech
  - [x] Speech Recognition
  - [x] Wake word detection
  - [x] Background listening
</details>

<details>
<summary>📱 Core Features</summary>

- **User Interface**
  - [x] Chat interface
  - [x] Settings management
  - [x] Voice input/output
  - [x] Message history

- **System Integration**
  - [x] Background service
  - [x] Lifecycle management
  - [x] Model loading/unloading
  - [x] Error recovery
</details>

## Future Enhancements 🚀

<details>
<summary>🤖 AI & Machine Learning</summary>

- **Offline LLM Integration**
  - [ ] On-device model processing
  - [ ] Model quantization
  - [ ] Model download management
  - [ ] Fallback system

- **Enhanced Memory System**
  - [ ] Memory categories
  - [ ] Memory search
  - [ ] Memory expiration
  - [ ] Memory tags
  - [ ] Export/import feature

- **Learning & Adaptation**
  - [ ] User preference learning
  - [ ] Response style adaptation
  - [ ] Conversation history analysis
  - [ ] Pattern recognition
  - [ ] Behavior learning
</details>

<details>
<summary>🎤 Voice & Communication</summary>

- **Voice Improvements**
  - [ ] Multiple voice options
  - [ ] Voice activity detection
  - [ ] Background noise cancellation
  - [ ] Voice profiles
  - [ ] Voice command shortcuts

- **Messaging Integration**
  - [ ] WhatsApp integration
  - [ ] SMS integration
  - [ ] Telegram integration
  - [ ] Message scheduling
  - [ ] Message templates

- **Email Integration**
  - [ ] Gmail/Outlook integration
  - [ ] Email composition
  - [ ] Email reading
  - [ ] Email scheduling
  - [ ] Email categorization
</details>

<details>
<summary>📱 App Integration & Automation</summary>

- **System Integration**
  - [ ] Screen brightness control
  - [ ] Volume control
  - [ ] Bluetooth management
  - [ ] WiFi control
  - [ ] Battery optimization

- **App Control**
  - [ ] App launching
  - [ ] Settings management
  - [ ] Permissions management
  - [ ] Updates checking
  - [ ] Usage statistics

- **Quick Actions**
  - [ ] One-tap actions
  - [ ] Custom shortcuts
  - [ ] Gesture controls
  - [ ] Widget controls
  - [ ] Quick reply templates
</details>

<details>
<summary>📅 Task & Time Management</summary>

- **Calendar Integration**
  - [ ] Google Calendar integration
  - [ ] Meeting scheduling
  - [ ] Event reminders
  - [ ] Recurring events
  - [ ] Calendar sharing

- **Task Management**
  - [ ] Todo list integration
  - [ ] Task prioritization
  - [ ] Deadline tracking
  - [ ] Task sharing
  - [ ] Progress tracking
</details>

<details>
<summary>🔒 Security & Privacy</summary>

- **Access Control**
  - [ ] App-specific permissions
  - [ ] Data access controls
  - [ ] Integration permissions
  - [ ] Privacy settings
  - [ ] Security policies

- **Data Protection**
  - [ ] End-to-end encryption
  - [ ] Secure storage
  - [ ] Data backup
  - [ ] Data recovery
  - [ ] Privacy controls
</details>

<details>
<summary>📊 Analytics & Insights</summary>

- **Usage Tracking**
  - [ ] App usage statistics
  - [ ] Integration usage
  - [ ] Command frequency
  - [ ] Response times
  - [ ] Error rates

- **Performance Monitoring**
  - [ ] Battery usage
  - [ ] Memory usage
  - [ ] CPU usage
  - [ ] Network usage
  - [ ] Storage usage
</details>

<details>
<summary>🔄 Integration & APIs</summary>

- **Third-party Apps**
  - [ ] Slack integration
  - [ ] Microsoft Teams
  - [ ] Zoom integration
  - [ ] Trello integration
  - [ ] Jira integration

- **Cloud Services**
  - [ ] Google Drive
  - [ ] Dropbox
  - [ ] OneDrive
  - [ ] iCloud
  - [ ] Backup services
</details>

<details>
<summary>🎨 UI/UX Improvements</summary>

- **Customization**
  - [ ] Dark/light theme
  - [ ] Custom voice commands
  - [ ] Custom shortcuts
  - [ ] Custom templates
  - [ ] Custom workflows

- **Accessibility**
  - [ ] Voice control
  - [ ] Gesture control
  - [ ] Screen reader support
  - [ ] High contrast mode
  - [ ] Font size adjustment
</details>

## In Progress 🏗️

<details>
<summary>Current Development</summary>

- **Voice Improvements**
  - [x] Basic TTS implementation
  - [x] Basic Speech Recognition
  - [ ] Multiple voice options
  - [ ] Voice activity detection
  - [ ] Background noise cancellation

- **Memory System**
  - [x] Basic memory storage
  - [x] Memory detection
  - [ ] Memory categories
  - [ ] Memory search
  - [ ] Memory expiration

- **UI/UX**
  - [x] Basic chat interface
  - [x] Settings screen
  - [ ] Dark/light theme
  - [ ] Custom voice commands
  - [ ] Gesture controls
</details>
