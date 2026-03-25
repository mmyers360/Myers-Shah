# Myers & Shah Website

## Site Structure

```
myersshah-site/
├── index.html                      ← Homepage
├── practice-areas.html             ← Practice Areas overview
├── attorneys.html                  ← Attorney profiles
├── trusts-and-estates.html         ← Trusts & Estates detail page
├── tax-planning.html               ← Tax Planning detail page
├── real-estate.html                ← Real Estate detail page
├── land-use-and-zoning.html        ← Land Use & Zoning detail page
├── trust-and-estate-litigation.html ← Trust & Estate Litigation detail page
├── images/
│   ├── mel-myers.jpg
│   └── ghezal-shah-myers.jpg
├── _redirects                      ← Netlify redirects (if needed)
└── README.md                       ← This file
```

## Deploying with GitHub + Netlify

### Step 1: Create a GitHub Repository

1. Go to https://github.com/new
2. Name it `myersshah-site` (or whatever you prefer)
3. Set it to **Private**
4. Click **Create repository**
5. Follow GitHub's instructions to upload files:
   - Click **"uploading an existing file"** link
   - Drag all the files from this folder into the upload area
   - Click **Commit changes**

### Step 2: Connect to Netlify

1. Log in at https://app.netlify.com
2. Click **Add new site** → **Import an existing project**
3. Select **GitHub** and authorize Netlify to access your repos
4. Select the `myersshah-site` repository
5. Leave build settings blank (no build command needed — it's plain HTML)
6. Click **Deploy site**

### Step 3: Connect Your Domain

1. In Netlify, go to **Site settings** → **Domain management**
2. Click **Add custom domain**
3. Enter `myersshah.com`
4. If your domain is already pointed to Netlify, it should connect automatically
5. Enable HTTPS under **SSL/TLS certificate**

### Making Updates

After the initial setup, any time you want to make a change:

1. Go to your repository on GitHub.com
2. Navigate to the file you want to edit
3. Click the pencil icon to edit
4. Make your changes
5. Click **Commit changes**
6. Netlify will automatically redeploy within ~30 seconds

### Key URLs

- **Calendly scheduling:** https://calendly.com/mmyers-myersshah
- **Email:** mmyers@myersshah.com  
- **Phone:** (703) 289-0452 and (202) 988-7553
