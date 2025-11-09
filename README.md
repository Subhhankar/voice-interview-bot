# 🎙️ Voice Interview Bot - Subhankar Saha

An AI-powered voice interview bot that responds to interview questions as Subhankar Saha, Machine Learning Engineer.

## 📋 Features

- **Voice Recognition**: Speak your questions naturally
- **AI-Powered Responses**: Uses Google Gemini API with personalized context
- **Text-to-Speech**: Bot speaks responses back to you
- **Text Alternative**: Type questions if voice is not available
- **Conversation Memory**: Maintains context throughout the interview
- **Responsive Design**: Works on desktop and mobile browsers

## 🚀 Quick Start (Local Development)

### Prerequisites

- Python 3.8 or higher
- Google Gemini API key (free from Google AI Studio)

### Step 1: Get Your Gemini API Key

1. Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Click "Get API Key"
3. Create a new API key
4. Copy the key

### Step 2: Setup Project

```bash
# Create project folder
mkdir voice-interview-bot
cd voice-interview-bot

# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On Mac/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### Step 3: Configure Environment

```bash
# Create .env file
cp .env.example .env

# Edit .env and add your API key
# GEMINI_API_KEY=your_actual_api_key_here
```

### Step 4: Create Folder Structure

```
voice-interview-bot/
├── app.py
├── requirements.txt
├── .env
├── .gitignore
└── templates/
    └── index.html
```

### Step 5: Run the Application

```bash
python app.py
```

Open your browser and go to: `http://localhost:5000`

## 🌐 Deployment to Render (FREE)

### Step 1: Prepare for Deployment

1. Create a `Procfile` (no extension):
```
web: gunicorn app:app
```

2. Ensure all files are ready:
   - `app.py`
   - `requirements.txt`
   - `templates/index.html`
   - `Procfile`
   - `.gitignore`

### Step 2: Push to GitHub

```bash
# Initialize git (if not already done)
git init
git add .
git commit -m "Initial commit - Voice Interview Bot"

# Create new repository on GitHub
# Then push your code
git remote add origin https://github.com/YOUR_USERNAME/voice-interview-bot.git
git branch -M main
git push -u origin main
```

### Step 3: Deploy on Render

1. Go to [Render.com](https://render.com) and sign up (free)
2. Click "New +" → "Web Service"
3. Connect your GitHub repository
4. Configure:
   - **Name**: `voice-interview-bot` (or your choice)
   - **Environment**: `Python 3`
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn app:app`
   - **Plan**: Free

5. Add Environment Variable:
   - Click "Environment"
   - Add: `GEMINI_API_KEY` = `your_actual_api_key`

6. Click "Create Web Service"

7. Wait 2-3 minutes for deployment

8. Your app will be live at: `https://voice-interview-bot-xxxx.onrender.com`

## 🌐 Alternative: Deploy to Railway (FREE)

1. Go to [Railway.app](https://railway.app)
2. Sign up with GitHub
3. Click "New Project" → "Deploy from GitHub repo"
4. Select your repository
5. Add environment variable: `GEMINI_API_KEY`
6. Railway auto-detects Python and deploys
7. Get your public URL from the deployment

## 🌐 Alternative: Deploy to Vercel (FREE)

Note: Vercel is primarily for frontend, but can handle Python with serverless functions.

1. Install Vercel CLI:
```bash
npm install -g vercel
```

2. Create `vercel.json`:
```json
{
  "builds": [
    {
      "src": "app.py",
      "use": "@vercel/python"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "app.py"
    }
  ]
}
```

3. Deploy:
```bash
vercel
```

4. Add environment variable in Vercel dashboard

## 📱 Browser Compatibility

**Voice Recognition works in:**
- ✅ Chrome (Desktop & Mobile)
- ✅ Edge (Desktop)
- ✅ Safari (iOS 14.5+)
- ⚠️ Firefox (Use text input instead)

**Text-to-Speech works in:**
- ✅ All modern browsers

## 🔧 Customization

### Update Personal Information

Edit the `PERSONAL_CONTEXT` section in `app.py`:

```python
PERSONAL_CONTEXT = """
You are [YOUR NAME], a [YOUR ROLE]...

YOUR BACKGROUND:
- Education: [YOUR EDUCATION]
- Current Role: [YOUR CURRENT JOB]
...
```

### Adjust Response Style

Modify the instructions in `PERSONAL_CONTEXT` to change:
- Tone (formal/casual)
- Response length
- Level of detail
- Personality traits

## 🐛 Troubleshooting

### "Speech recognition not supported"
- Use Chrome or Edge browser
- Use the text input as an alternative

### "API key not configured"
- Ensure `.env` file exists with `GEMINI_API_KEY`
- Restart the application after adding the key

### Microphone not working
- Check browser permissions
- Ensure HTTPS is enabled (required for mic access)
- Try the text input instead

### "Error connecting to server"
- Check if Flask app is running
- Verify API key is valid
- Check internet connection

## 💡 Usage Tips

1. **Ask Clear Questions**: Speak clearly and pause before stopping
2. **One Question at a Time**: Better results with focused questions
3. **Use Text Input**: If voice is problematic, typing works great
4. **Reset Chat**: Use reset button to start fresh conversation

## 📊 Sample Interview Questions

- What should we know about your life story?
- What's your #1 superpower?
- What are your top 3 growth areas?
- What misconception do coworkers have about you?
- How do you push your boundaries?
- Tell me about your most challenging project
- Why are you interested in this position?

## 🔐 Security Notes

- **Never commit `.env` file** (it's in `.gitignore`)
- **Use environment variables** for API keys in production
- **Regenerate API keys** if accidentally exposed
- **Set API quotas** to prevent unexpected costs

## 📈 API Costs

Google Gemini API (Free Tier):
- 60 requests per minute
- 1,500 requests per day
- FREE for testing and small projects

Monitor your usage at: [Google AI Studio](https://makersuite.google.com/)

## 🎯 Submission Checklist

- ✅ Code runs without errors
- ✅ Voice recognition works (in Chrome/Edge)
- ✅ Text input alternative provided
- ✅ Responses are personalized
- ✅ Deployed to live URL
- ✅ No API key in code
- ✅ Works for non-technical users
- ✅ Professional UI/UX
- ✅ README included

## 📧 Support

For issues or questions:
- Check troubleshooting section above
- Review browser console for errors
- Ensure API key is valid and has quota remaining

## 📄 License

This project is created for the 100x interview assignment.

---

**Created by Subhankar Saha**  
Machine Learning Engineer | AI Enthusiast  
📧 subhankar.datascience@gmail.com