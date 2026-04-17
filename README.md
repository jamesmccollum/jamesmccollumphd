# jamesmccollumphd.com

Static site. No build step, no dependencies.

## File structure

```
jamesmccollumphd/
  index.html
  style.css
  assets/
    jimheadshot1-web.jpg   ← headshot
    logo.png               ← add your horizontal logo PNG here
```

## Setup

### 1. Formspree (contact form)
- Sign up at https://formspree.io
- Create a new form, copy the endpoint ID
- In index.html, replace `YOUR_FORMSPREE_ID` in the form action URL:
  `<form action="https://formspree.io/f/YOUR_FORMSPREE_ID">`

### 2. GitHub
- Create a new repo at github.com
- Push this folder:
  ```
  git init
  git add .
  git commit -m "initial"
  git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
  git push -u origin main
  ```

### 3. Cloudflare Pages
- Go to Cloudflare dashboard → Pages → Create a project
- Connect your GitHub repo
- Build settings: leave blank (no build command, output directory is `/`)
- Deploy

### 4. Custom domain
- In Cloudflare Pages, go to Custom Domains → Add domain
- Enter jamesmccollumphd.com
- Since your domain is already on Cloudflare DNS, it'll connect automatically

## Making edits
Edit index.html or style.css locally, then:
```
git add . && git commit -m "your message" && git push
```
Cloudflare redeploys automatically in ~30 seconds.

## To add your logo
- Add logo PNG to assets/
- In index.html, replace the `.nav-name` span with:
  `<a href="/"><img src="assets/logo.png" alt="James McCollum" class="nav-logo" /></a>`
- In style.css, add:
  `.nav-logo { height: 36px; width: auto; }`
