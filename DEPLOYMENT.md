# StyleMate Deployment Guide

## Quick Start Commands

After downloading and extracting StyleMate to your PC:

### 1. Open in VS Code
```bash
# Navigate to your StyleMate folder
cd path/to/StyleMate

# Open in VS Code
code .
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Set Up Environment
```bash
# Create environment file
echo "GEMINI_API_KEY=your_api_key_here" > .env

# Create uploads directory
mkdir uploads
```

### 4. Start Development Server
```bash
npm run dev
```

### 5. Access Your App
Open browser to: `http://localhost:5000`

## Production Deployment

### Build for Production
```bash
# Build the application
npm run build

# Start production server
npm start
```

### Environment Variables Needed
```env
GEMINI_API_KEY=your_gemini_api_key
NODE_ENV=production
PORT=5000
```

## Platform-Specific Deployment

### Vercel (Recommended for Frontend)
```bash
npm install -g vercel
vercel login
vercel --prod
```

### Railway (Full-Stack)
1. Push to GitHub
2. Connect to Railway
3. Add environment variables
4. Deploy automatically

### Replit (Easiest)
1. Upload zip to Replit
2. Add GEMINI_API_KEY to Secrets
3. Click Run

### Self-Hosted Server
```bash
# On your server
git clone your-repo
cd StyleMate
npm install --production
npm run build

# Using PM2
npm install -g pm2
pm2 start npm --name "stylemate" -- start
pm2 save
pm2 startup
```

## File Structure for Deployment
```
StyleMate/
├── dist/           # Built frontend files
├── server/         # Backend server files
├── uploads/        # Image storage (create this)
├── package.json    # Dependencies
├── .env           # Environment variables
└── README.md      # This file
```

That's it! Your StyleMate app will be ready to analyze clothing and suggest outfits using AI.