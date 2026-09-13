# Mirabel Maternity Website

Static site (plain HTML/CSS/JS, no build step) for Mirabel Maternity doula
services. This is a completely separate project from any other site — nothing
here touches the live mirabelmaternity.com site until you choose to point the
domain here (see "Going live" below).

## What's in here

- `index.html` — Home
- `about.html` — About the doula
- `services.html` — Services & packages
- `testimonials.html` — Client testimonials
- `faq.html` — Frequently asked questions
- `contact.html` — Contact form + direct contact info
- `assets/` — CSS, JS, images

## Before you publish: fill in the placeholders

Search each HTML file for text in `[brackets]` — that's everything that needs
real information before this goes live. Key things to gather:

- Doula's name and bio (`about.html`)
- Real certifications/training — **never list a certification that hasn't
  actually been completed**
- Real pricing and package inclusions (`services.html`)
- Real testimonials, with permission from each client (`testimonials.html`)
- Real phone number, email, and exact service area (footer on every page,
  plus `contact.html`)
- A real photo (replace the dashed placeholder box in the hero sections)
- Cited statistics on the homepage "Why a Doula" section, or remove that
  section if you don't have sources handy

## Setting up the contact form (free, ~5 minutes)

The contact form uses [Web3Forms](https://web3forms.com) — free, no monthly
cost, no card required, unlimited submissions.

1. Go to https://web3forms.com and enter the email where you want form
   submissions delivered.
2. You'll get an Access Key by email.
3. In `contact.html`, find `YOUR_ACCESS_KEY_HERE` and replace it with that key.
4. Commit and push — form submissions will now land in that inbox.

## Deploying for free on Cloudflare Pages

This costs $0/month for a static site like this one — no credit card needed.

1. Go to https://dash.cloudflare.com → **Workers & Pages** → **Create** →
   **Pages** → **Connect to Git**.
2. Authorize Cloudflare to access the `mirabelmaternity-site` GitHub repo and
   select it.
3. Build settings: leave **Framework preset** as "None", **Build command**
   blank, **Build output directory** as `/` (root). There's nothing to build —
   it's plain HTML.
4. Click **Save and Deploy**. Cloudflare gives you a free URL like
   `mirabelmaternity-site.pages.dev` to preview and share.
5. Every push to the `main` branch auto-deploys a new version. Pull requests
   get their own preview URL automatically.

## Going live on the real domain (when you're ready)

This step is the only one that touches anything live, and it's fully
reversible.

1. In the Cloudflare Pages project, go to **Custom domains** → **Set up a
   custom domain** → enter `mirabelmaternity.com` (and `www.mirabelmaternity.com`
   if you use both).
2. Cloudflare will tell you exactly what DNS record to add. If the domain's
   DNS is not already on Cloudflare, you'll add/update records at wherever the
   domain is currently registered.
3. Nothing switches over until you actually change that DNS record. Until
   then, the current live site keeps running exactly as it does today, and
   this new site stays reachable only at its `.pages.dev` preview URL.
4. If anything looks wrong after cutover, you can point DNS back to the old
   host at any time.
