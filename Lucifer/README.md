Lucifer — Static Site
=====================

A small static site that presents a stylized book layout for "Lucifer - The Light-Bringer's Shadow".
This folder contains a single-page static website (`index.html`) and an `images/` directory used by the page.

Preview (local)
----------------
The site is static HTML/CSS and requires no build step. To preview locally you can use one of these quick methods.

PowerShell (Python's built-in server):

```powershell
cd e:\Lucifer\Lucifer
python -m http.server 8000
# then open http://localhost:8000 in your browser
```

Node (http-server package):

```powershell
npm install -g http-server
cd e:\Lucifer\Lucifer
http-server -p 8000
# then open http://localhost:8000
```

What is in this folder
----------------------
- `index.html` — the main static page (book layout, typography, and styling).
- `images/` — images referenced by `index.html` (cover, map, art, etc.).
- `NETLIFY.md` — previously added quick Netlify instructions.
- `README.md` — this file.

Run notes
----------
- The page links to Google Fonts and a remote texture image. You need an internet connection for fonts and that texture to load.
- All assets referenced by the HTML should be present in `images/`. If an image is missing the browser will show an image placeholder.

Deploying to Netlify (quick)
---------------------------
Two recommended ways to publish to Netlify are:

1) Netlify Drop (fastest — no CLI or git required)
   - Open https://app.netlify.com/drop
   - Drag the contents of this folder (or a .zip of the files) onto the page.
   - Netlify uploads the files and gives you a public URL instantly.

2) Netlify CLI (recommended for repeat updates from this machine)
   - Prerequisite: Node.js + npm installed: https://nodejs.org/
   - Install the CLI:

```powershell
npm install -g netlify-cli
```

   - Login (this opens a browser to sign in):

```powershell
netlify login
```

   - Deploy (from inside this folder):

```powershell
cd e:\Lucifer\Lucifer
netlify deploy --dir=. --prod
```

   - On first run the CLI will prompt you to create a new site or link to an existing one; follow the prompts and choose a name or accept the generated one.

Optional: Connect a Git repo and enable continuous deploy
--------------------------------------------------------
- Initialize git, push to GitHub, then in Netlify choose "New site from Git" and connect your repo. Netlify will auto-deploy on every push.

```powershell
cd e:\Lucifer\Lucifer
git init
git add .
git commit -m "Initial site"
# create a GitHub repo and then:
git remote add origin https://github.com/<username>/<repo>.git
git branch -M main
git push -u origin main
```

Tips and troubleshooting
------------------------
- If fonts or textures don't load, check your internet connection or allow mixed content if you're testing via `file://` (prefer the local server instead).
- If an image shows a broken link, confirm the filename and path inside the `images/` folder matches the `src` attribute in `index.html`.
- To stop the local Python server press Ctrl+C in the terminal where it's running.

License & credits
------------------
- This repo contains HTML/CSS and images. Verify you have rights to distribute any images included in `images/` before publishing publicly.
- Add or change the license by adding a `LICENSE` file if you want specific reuse terms.

If you want me to:
- finish the Netlify CLI deploy now and walk you through the prompts, or
- prepare a GitHub repo and push (you'll need to provide credentials or run the final git push),
let me know which and I'll continue.
