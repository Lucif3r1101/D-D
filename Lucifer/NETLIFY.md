Netlify deployment instructions
=============================

This file explains two quick ways to publish the static site in this folder (`index.html` + `images/`) to Netlify:

1) Netlify Drop (fastest, no CLI or git required)
2) Netlify CLI (recommended if you plan to update frequently from this machine)

---

Netlify Drop (drag & drop) — fastest
-----------------------------------

1. Open https://app.netlify.com/drop in your browser.
2. In your file explorer, compress or select the contents of this folder (`index.html` and the `images/` folder) and drag them to the Drop page.
3. Netlify will upload the files and provide a public URL like `https://clever-name-12345.netlify.app`.
4. Share that URL with anyone.

Notes:
- Netlify Drop publishes instantly and is persisted to a hosted site, but you won't get a connected git repo automatically. To have source control and continuous deploy, use Netlify's Git integration.

---

Netlify CLI (recommended for repeated updates)
--------------------------------------------

Prerequisites:
- Node.js and npm installed. Download from https://nodejs.org if needed.

Install Netlify CLI (PowerShell):

```powershell
npm install -g netlify-cli
```

Login (opens browser):

```powershell
netlify login
```

One-time quick deploy from this folder (useful for a single-site deploy):

```powershell
# from inside e:\Lucifer\Lucifer
netlify deploy --dir=. --prod
```

Notes about the `deploy` command:
- `--dir=.` tells Netlify to publish the current directory contents (so make sure `index.html` and `images/` are present).
- On first run you'll be prompted to link or create a Netlify site. Choose "Create & configure a new site" if asked.
- You can set a site name during setup (if the name is available) or accept a random one.

To create a repeatable workflow with git:

1. Initialize git (if not already):

```powershell
cd e:\Lucifer\Lucifer
git init
git add .
git commit -m "Initial site"
```

2. Push to GitHub and enable Netlify continuous deploy (on Netlify: Connect to your Git provider and pick the repo).

---

Stopping the local preview server
---------------------------------
If you started the local Python server (the preview), stop it with Ctrl+C in the terminal running it.

---

Custom domain & HTTPS
----------------------
- On Netlify, you can set a custom domain on the site's dashboard. Netlify provisions HTTPS automatically with Let's Encrypt.

---

If you want, I can:
- walk you through Netlify Drop right now while you share your screen, or
- provide the exact commands for the CLI and help you run them, or
- create a simple README or .gitignore in this folder and stage the git commands for you to run.

End of instructions.
