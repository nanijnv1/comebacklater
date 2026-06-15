# comebacklater.in

A funny, interactive "come back later" page. One self-contained `index.html` — no build step, no dependencies.

## What it does
- Big animated **"Come back later."** headline
- Rotating absurd excuses for why the site isn't ready
- A **ridiculous countdown** that sometimes counts *up*
- An **"Enter the site anyway" button that dodges your cursor** (hover on desktop, tap on mobile)
- Persists how many times you've visited + how many times the button dodged you (`localStorage`)
- Persist long enough (20 dodges) → **confetti + a useless reward coupon**
- "reset my shame" link in the footer

## Preview locally
Just open the file:
```bash
open index.html
```
Or serve it:
```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Deploy (pick one)

### Netlify (drag & drop — easiest)
1. Go to https://app.netlify.com/drop
2. Drag this folder in. Done.
3. Site settings → Domain management → add `comebacklater.in` and follow the DNS steps.

### Vercel
```bash
npx vercel        # from this folder, follow prompts
npx vercel --prod
```
Then add `comebacklater.in` under the project's Domains.

### GitHub Pages
1. Push this folder to a repo.
2. Repo → Settings → Pages → deploy from `main` / root.
3. Add `comebacklater.in` as the custom domain (creates a `CNAME` file).

## DNS for comebacklater.in
At your registrar, point the domain at your host:
- **Apex (`comebacklater.in`)**: an `A`/`ALIAS` record per your host's instructions.
- **`www`**: a `CNAME` to your host's target.

Each host shows the exact records when you add the custom domain.

## Customize
Everything lives in `index.html`:
- Edit the `excuses` array for your own jokes.
- Tweak colors in the `:root` CSS variables.
- Change the reward threshold (`state.dodges >= 20`) or the coupon text.
