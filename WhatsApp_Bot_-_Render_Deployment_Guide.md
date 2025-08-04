# WhatsApp Bot - Render Deployment Guide

## Why Render?

Render is an excellent alternative to Vercel for hosting Node.js applications with these advantages:
- **No Sleep Mode**: Unlike Heroku, your bot stays active 24/7
- **Free Tier**: Generous free tier with 750 hours per month
- **Git Integration**: Automatic deployments from GitHub
- **Custom Domains**: Free custom domain support
- **Zero Downtime**: Seamless deployments without interruption

## Step-by-Step Deployment Instructions

### Step 1: Prepare Your GitHub Repository

1. **Create a new repository on GitHub**:
   - Go to [github.com/new](https://github.com/new)
   - Repository name: `whatsapp-bot-render`
   - Set to **Public** (required for free deployment)
   - Click "Create repository"

2. **Upload all files** from this project to your GitHub repository:
   - Include all files, especially:
     - `index.js` (main bot file)
     - `package.json` (dependencies)
     - `render.yaml` (Render configuration)
     - `session/creds.json` (your WhatsApp session)
     - All `lib/` folder contents

### Step 2: Deploy on Render

1. **Create Render Account**:
   - Go to [render.com](https://render.com)
   - Click "Get Started for Free"
   - Sign up with GitHub (recommended for easy integration)

2. **Create New Web Service**:
   - On Render dashboard, click "New +"
   - Select "Web Service"
   - Connect your GitHub repository `whatsapp-bot-render`
   - Click "Connect"

3. **Configure Service Settings**:
   - **Name**: `whatsapp-bot-anita` (or your preferred name)
   - **Environment**: `Node`
   - **Region**: Choose closest to your location
   - **Branch**: `main` (or your default branch)
   - **Build Command**: `npm install`
   - **Start Command**: `npm start`

4. **Environment Variables** (Important):
   The render.yaml file includes all necessary environment variables, but you can also set them manually:
   
   ```
   OWNER_NUMBER = 923051625609
   BOT_NAME = 𝐐𝐔𝐄𝐄𝐍_𝐀𝐍𝐈𝐓𝐀-𝐕𝟒
   PREFIX = .
   PUBLIC = true
   ```

5. **Select Plan**:
   - Choose **Free** plan
   - Click "Create Web Service"

6. **Deploy**:
   - Render will automatically start building and deploying
   - Wait for deployment to complete (usually 2-5 minutes)
   - You'll get a live URL like: `https://whatsapp-bot-anita.onrender.com`

### Step 3: Bot Configuration

Your bot is now live! Here are the details:

- **Owner Number**: 923051625609
- **Bot Prefix**: `.` (dot)
- **Bot Name**: 𝐐𝐔𝐄𝐄𝐍_𝐀𝐍𝐈𝐓𝐀-𝐕𝟒
- **Session**: Pre-configured with your session data
- **Uptime**: 24/7 (no sleep mode)

### Step 4: Using Your Bot

1. **WhatsApp Connection**: Bot connects automatically using your session
2. **Commands**: Send messages with `.` prefix (e.g., `.help`, `.menu`)
3. **Owner Commands**: Only you (923051625609) can use owner-specific commands

## Render Free Tier Limits

- **750 hours per month** (more than enough for 24/7 operation)
- **512 MB RAM**
- **0.1 CPU**
- **No sleep mode** (unlike Heroku)
- **Automatic SSL**
- **Custom domains**

## Advantages Over Other Platforms

### vs Vercel:
- ✅ No serverless function time limits
- ✅ Persistent connections (better for WhatsApp bots)
- ✅ No cold starts

### vs Heroku:
- ✅ No sleep mode on free tier
- ✅ More generous resource limits
- ✅ Better performance

### vs Railway:
- ✅ More predictable pricing
- ✅ Better documentation
- ✅ Simpler deployment process

## Troubleshooting

1. **Bot Not Responding**: Check Render service logs in dashboard
2. **Build Failures**: Ensure all dependencies are in package.json
3. **Session Issues**: May need to regenerate session if it expires
4. **Memory Issues**: Monitor usage in Render dashboard

## Monitoring Your Bot

- **Render Dashboard**: Monitor CPU, memory, and logs
- **Service URL**: Your bot's public endpoint
- **Automatic Restarts**: Render automatically restarts if service crashes
- **Health Checks**: Built-in monitoring ensures uptime

## Updates and Maintenance

1. **Code Updates**: Push to GitHub, Render auto-deploys
2. **Environment Variables**: Update in Render dashboard
3. **Scaling**: Upgrade to paid plans for more resources
4. **Backups**: Session data persists across deployments

Your WhatsApp bot is now running 24/7 on Render! 🚀

## Support

If you encounter issues:
1. Check Render service logs
2. Verify environment variables
3. Ensure session data is valid
4. Monitor resource usage

Render provides excellent documentation and support for troubleshooting.

