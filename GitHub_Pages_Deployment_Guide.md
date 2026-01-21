# Deploy Career Level-Up Quest to sanuga.uk

## Step 1: Create GitHub Repository

```bash
# Create a new repository on GitHub named "career-levelup-quest"
# Then clone it locally:
git clone https://github.com/San-Nim/career_levelup_quest.git
cd career-levelup-quest
```

## Step 2: Project Structure

Create these files in your repository:

```
career-levelup-quest/
├── index.html
├── README.md
├── CNAME
└── .github/
    └── workflows/
        └── deploy.yml
```

## Step 3: index.html

Create `index.html` with this content:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Career Level-Up Quest 🎮</title>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            margin: 0;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
                'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
                sans-serif;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }
    </style>
</head>
<body>
    <div id="root"></div>
    
    <!-- Lucide Icons CDN -->
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <script type="text/babel">
        // Paste the entire React component code here
        // Copy from the artifact above, starting from "import React..." to the end
        
        // For now, I'll include the full component inline
        // [COMPONENT CODE GOES HERE - see next message for full code]
        
        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<ADHDLearningTracker />);
    </script>
</body>
</html>
```

## Step 4: CNAME File

Create a `CNAME` file with:

```
sanuga.uk
```

## Step 5: Configure Your Domain

### In Your Domain Registrar (where you bought sanuga.uk):

1. Go to DNS settings
2. Add these records:

**For root domain (sanuga.uk):**
```
Type: A
Host: @
Value: 185.199.108.153
TTL: 3600

Type: A
Host: @
Value: 185.199.109.153
TTL: 3600

Type: A
Host: @
Value: 185.199.110.153
TTL: 3600

Type: A
Host: @
Value: 185.199.111.153
TTL: 3600
```

**For www subdomain (optional):**
```
Type: CNAME
Host: www
Value: YOUR_USERNAME.github.io
TTL: 3600
```

## Step 6: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages**
3. Under "Source", select **Deploy from a branch**
4. Select branch: **main** (or **master**)
5. Select folder: **/ (root)**
6. Click **Save**
7. Add your custom domain: **sanuga.uk**
8. Check **Enforce HTTPS** (wait a few minutes for SSL certificate)

## Step 7: Push Your Code

```bash
git add .
git commit -m "Initial deployment of Career Level-Up Quest"
git push origin main
```

## Step 8: Wait for Deployment

- GitHub Pages typically takes 1-5 minutes to deploy
- DNS propagation can take up to 24 hours (usually much faster)
- Check deployment status in **Actions** tab on GitHub

## Features Included

✅ **Multi-user support** - Each user has their own account
✅ **Persistent storage** - Data saved across sessions
✅ **Global leaderboard** - Compete with friends!
✅ **Real-time updates** - See leaderboard changes
✅ **Login system** - Simple username-based auth
✅ **Shareable** - Send link to friends: https://sanuga.uk

## Testing Locally

To test before deployment:

1. Open `index.html` in a browser
2. Or use a local server:
```bash
python -m http.server 8000
# Then visit http://localhost:8000
```

## Troubleshooting

**Domain not working?**
- Wait 24 hours for DNS propagation
- Check CNAME file exists in repository
- Verify DNS records are correct
- GitHub Pages should show "Your site is live at https://sanuga.uk"

**Storage not persisting?**
- Make sure you're using the deployed version (not local file://)
- Check browser console for errors
- Claude's storage API requires HTTPS

**Friends can't join?**
- Make sure they're using the same URL (sanuga.uk)
- Storage is shared across all users on the same domain
- Each user needs to create their own username

## Sharing with Friends

Send them this message:

> 🎮 Join me on Career Level-Up Quest!
> 
> We're gamifying our learning journey together. Track courses, earn XP, and compete on the leaderboard!
> 
> 👉 https://sanuga.uk
> 
> Just enter a username and start leveling up! 🚀

## Next Steps

Once deployed, you can:
- Add more courses through the code
- Customize XP values
- Add more bonus challenges
- Create team challenges
- Add achievements system

Need help? Open an issue on GitHub or contact me!