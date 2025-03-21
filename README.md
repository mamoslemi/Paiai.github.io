# 🤖 Aibot - Advanced AI-Powered Telegram Bot

> 🚀 A powerful, extensible Telegram bot that combines AI capabilities with a modular plugin system.

## ✨ Features

🧠 **AI Integration**
- 💬 Natural language conversations with GPT models
- 🎯 Context-aware responses
- 📝 Custom prompt management
- 🔄 Multiple chat sessions

🛠️ **Developer Tools**
- 💻 Code generation and analysis
- 🐞 Debugging assistance
- 🔍 Code optimization
- 📚 Code explanation

🔌 **Plugin System**
- 🧩 Easy-to-create plugins
- ⚡ Dynamic loading/unloading
- 🎮 Plugin state management
- 🔒 Security controls

🌐 **Web Integration**
- 🔍 Integrated web search
- 📰 News article fetching
- 🔗 URL processing
- 📊 Data extraction

👥 **User Management**
- 👤 User authentication
- 🎭 Role-based access
- 📊 Usage statistics
- ⚙️ User preferences

🛡️ **Security & Control**
- 🔐 API key management
- ⚡ Rate limiting
- 📝 Logging system
- 🚫 Input validation

## 🏗️ Project Structure

```
Aibot/
├── 📁 handlers/           # Message handlers
│   ├── 🔐 auth_handlers.py
│   ├── 💬 chat_handlers.py
│   ├── 🔌 plugin_handlers.py
│   └── 📝 prompt_handlers.py
├── 📁 plugins/           # Plugin system
│   ├── 🧩 base.py
│   ├── 💻 coder.py
│   └── 🎮 manager.py
├── 🤖 bot.py            # Main bot logic
├── ⚙️ config.py         # Configuration
├── 🗄️ database.py       # Database operations
├── 🧠 ai_model.py       # AI integration
├── 📨 message_processor.py
├── 🌐 web_search.py     # Web integration
├── ⚡ rate_limiter.py    # Rate limiting
└── 🏃 run.py            # Entry point
```

## 🚀 Quick Start

### 📋 Prerequisites
- Python 3.8+
- Telegram Bot Token
- OpenAI API Key
- Tavily API Key (for web search)

### 🔧 Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/aibot.git
cd aibot
```

2. **Create virtual environment**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Configure environment**
Create `.env` file:
```env
BOT_TOKEN=your_telegram_bot_token
OPENAI_API_KEY=your_openai_api_key
TAVILY_API_KEY=your_tavily_api_key
ADMIN_IDS=123456789,987654321
```

5. **Initialize database**
```bash
python -c "from database import init_db; init_db()"
```

6. **Run the bot**
```bash
python run.py
```

## 🎯 Usage

### 🤖 Basic Commands
- `/start` - Start the bot
- `/help` - Show help message
- `/newchat` - Start new chat
- `/prompt` - Manage prompts
- `/settings` - Bot settings

### 💻 Code Commands
- `/code` - Generate code
- `/analyze` - Analyze code
- `/debug` - Debug code
- `/optimize` - Optimize code
- `/explain` - Explain code

### 🔌 Plugin Commands
- `/plugins` - List plugins
- `/enable` - Enable plugin
- `/disable` - Disable plugin
- `/create` - Create plugin

## 🧩 Extending the Bot

### 📝 Creating a Plugin

1. Create new file in `plugins/` directory:
```python
from plugins.base import BasePlugin

class MyPlugin(BasePlugin):
    def __init__(self):
        super().__init__(
            name="my_plugin",
            description="My awesome plugin"
        )

    async def initialize(self) -> bool:
        return True

    async def execute(self, action: str, *args, **kwargs):
        # Implement your logic here
        pass
```

2. Register in `plugins/__init__.py`:
```python
from .my_plugin import MyPlugin
__all__ = [..., "MyPlugin"]
```

### 🎮 Adding Handlers

1. Create handler in `handlers/` directory:
```python
from aiogram import types
from aiogram.fsm.context import FSMContext

async def my_handler(message: types.Message, state: FSMContext):
    # Implement handler logic
    pass
```

2. Register in `bot.py`:
```python
@dp.message(MyState.waiting)
async def handle_my_state(message: types.Message, state: FSMContext):
    await my_handler(message, state)
```

## 🔧 Configuration

### ⚙️ Available Settings
| Setting | Description | Default |
|---------|-------------|---------|
| `BOT_TOKEN` | Telegram Bot Token | Required |
| `OPENAI_API_KEY` | OpenAI API Key | Required |
| `OPENAI_MODEL` | GPT Model | gpt-3.5-turbo |
| `MAX_HISTORY` | Chat History Size | 10 |
| `RATE_LIMIT` | Messages per Minute | 30 |

## 🤝 Contributing

1. 🍴 Fork the repository
2. 🌿 Create feature branch (`git checkout -b feature/amazing`)
3. 💾 Commit changes (`git commit -am 'Add amazing feature'`)
4. 🚀 Push branch (`git push origin feature/amazing`)
5. 📝 Open Pull Request

## 🐞 Troubleshooting

### 🔍 Common Issues

1. **🔴 Database Errors**
   - Check file permissions
   - Verify schema version
   - Ensure proper initialization

2. **🔴 API Errors**
   - Verify API keys
   - Check rate limits
   - Validate endpoints

3. **🔴 Plugin Issues**
   - Check initialization
   - Verify dependencies
   - Review logs

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Aiogram](https://github.com/aiogram/aiogram) for the amazing bot framework
- [OpenAI](https://openai.com) for the GPT API
- [Tavily](https://tavily.com) for the web search API

---
Made with ❤️ by [Your Name] 
