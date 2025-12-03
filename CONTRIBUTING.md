# 🤝 Contributing Guide

Thank you for your interest in contributing! Here's how to get started.

## 📋 **Prerequisites**

- Python 3.10+
- Git
- Google Gemini API key
- WhatsApp Meta Business account (for testing)

## 🚀 **Getting Started**

### **1. Fork & Clone**
```bash
git clone https://github.com/YOUR_USERNAME/job-hunter.git
cd job-hunter
git remote add upstream https://github.com/saiyudh/job-hunter.git
```

### **2. Create Branch**
```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/bug-description
```

### **3. Setup Development Environment**
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
# Add your API keys to .env
```

### **4. Make Changes**
- Follow PEP 8 style guide
- Add docstrings to functions
- Write tests for new features

### **5. Test Locally**
```bash
python examples/test_commands.py
python webhook_server.py
```

### **6. Commit & Push**
```bash
git add .
git commit -m "feat: add amazing feature"
git push origin feature/your-feature-name
```

### **7. Open Pull Request**
- Describe your changes
- Reference any related issues
- Provide test results

## 📝 **Code Standards**

### **Python Style**
```python
# Good ✅
def analyze_job_skills(job: dict) -> dict:
    """Extract and match job skills with CV.
    
    Args:
        job: Job dict with description
    
    Returns:
        dict: Skills analysis results
    """
    try:
        # Implementation
        pass
    except Exception as e:
        logger.error(f"Error: {e}")
        return {}
```

### **Error Handling**
- Wrap ALL external calls in try/except
- Never crash on bad data
- Log errors with context
- Return sensible defaults

### **Documentation**
- Docstrings for all functions
- Comments for complex logic
- Update README for new features
- Include examples in docstrings

## 🐛 **Bug Reports**

Include:
- Python version
- Error message/traceback
- Steps to reproduce
- Expected vs actual behavior

## 💡 **Feature Requests**

Describe:
- Use case
- Why it's valuable
- How it works
- Related features

## 🎯 **Areas to Contribute**

### **High Priority**
- [ ] Multi-LLM support (OpenAI fallback)
- [ ] Auto-Apply feature (CV/Cover Letter)
- [ ] Gmail response tracking
- [ ] Database persistence (instead of Sheets)

### **Medium Priority**
- [ ] Advanced filtering
- [ ] Custom scoring rules
- [ ] Performance optimization
- [ ] Additional scraping sources

### **Low Priority**
- [ ] UI dashboard
- [ ] Mobile app
- [ ] Analytics reports

## 📚 **Project Structure**

```
agents/           # AI agents (stateless, single responsibility)
utils/            # Helper utilities (sheets, dedupe, notifications)
config/           # Configuration management
webhook_server.py # WhatsApp webhook entry point
main.py           # Batch processing entry point
```

## ✅ **Pull Request Checklist**

- [ ] Code follows PEP 8
- [ ] All docstrings present
- [ ] Error handling added
- [ ] Tests written/passed
- [ ] README updated
- [ ] No breaking changes
- [ ] Commit messages are clear

## 🤖 **AI Development Guidelines**

When adding Gemini AI features:

1. **Prompt Engineering**
   - Test prompts thoroughly
   - Handle edge cases
   - Add fallback logic

2. **Error Handling**
   - Catch API errors
   - Implement retries
   - Use fallback extraction

3. **Performance**
   - Cache results when possible
   - Batch requests efficiently
   - Monitor token usage

## 📊 **Testing**

### **Manual Testing**
```bash
python examples/test_commands.py

# Or test specific command
python -c "
from utils.whatsapp_notifier import command_handler
result = command_handler.handle_command('10 python berlin')
"
```

### **WhatsApp Testing**
```bash
# 1. Start webhook
python webhook_server.py

# 2. Start ngrok
ngrok http 5000

# 3. Configure Meta webhook URL

# 4. Send WhatsApp message
```

## 📞 **Questions?**

- 💬 GitHub Discussions
- 📧 Email: saiyudh.mannan@gmail.com
- 🐙 Open an Issue

## 🙏 **Code of Conduct**

- Be respectful and inclusive
- No harassment or discrimination
- Constructive feedback only
- Report violations to maintainers

---

**Happy contributing!** 🚀
