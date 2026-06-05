# Champions Academy — Website

A complete sports academy website powered by **Decap CMS** (free, no monthly fees).
Your admin edits every section through a clean visual panel at `/admin`. Visitors just see the live site.

---

## 📁 What's inside

```
champions-academy/
├── index.html              ← The main site (loads content dynamically)
├── netlify.toml            ← Netlify deployment config
├── admin/
│   ├── index.html          ← The CMS admin panel
│   └── config.yml          ← Defines every editable section
└── content/
    ├── settings/           ← Hero, contact, about, achievements
    ├── sports/             ← 8 sports (1 file per sport)
    ├── coaches/            ← Coach profiles (1 file per coach)
    ├── offers/             ← Top offers strip
    ├── pricing/            ← Pricing plans
    ├── schedule/           ← Weekly training slots
    ├── testimonials/       ← Parent reviews
    └── news/               ← News & updates
```

---

## 🚀 Deployment (one-time setup — ~20 minutes)

### Step 1 — Push to GitHub
1. Create a free account at [github.com](https://github.com)
2. Create a new repository, e.g. `champions-academy`
3. Upload everything in this folder (drag & drop on github.com works)

### Step 2 — Deploy on Netlify
1. Create a free account at [netlify.com](https://netlify.com)
2. Click **"Add new site → Import an existing project"**
3. Connect GitHub, pick your repo
4. Build settings: leave everything default, click **Deploy**
5. Your site goes live at a URL like `https://champions-academy-abc.netlify.app`

### Step 3 — Enable the CMS (Identity + Git Gateway)
1. In Netlify dashboard, go to **Site → Identity → Enable Identity**
2. Scroll to **Registration preferences → Invite only**
3. Scroll to **Git Gateway → Enable Git Gateway**
4. Go to **Identity → Invite users** → invite your admins' emails
5. Each admin accepts the email invite, sets a password

### Step 4 — Custom domain (optional)
**Site settings → Domain management → Add custom domain** — point your `championsacademy.com` here.

---

## ✏️ How the admin edits content

Admin goes to `https://your-site.com/admin` → logs in → sees this menu:

| Section | What they edit |
|---|---|
| 🏠 Site Settings | Academy name, hero title, announcement bar, stats, contact info, hours, WhatsApp number, app URL, about section |
| ⚽ Sports | Add/edit/delete sports. Each sport has name, emoji, ages, level, tags, price, color, image |
| 👨‍🏫 Coaches | Add/edit/delete coaches. Photo, certification, achievements, sport |
| 🎁 Offers | Top of-page offer cards — title, badge, subtitle |
| 💰 Pricing | Plans, old/new price, features, mark as "popular" |
| 📅 Schedule | Weekly training slots — day, time, sport, coach, age |
| 💬 Testimonials | Parent reviews — quote, name, rating, mark one as "featured" |
| 📰 News | Tournament results, announcements, camps |
| 🏆 Achievement Bar | 4 big stats at the bottom of testimonials |

**Every save triggers an automatic site rebuild in ~30 seconds.** Done.

---

## 🔑 Two roles (as agreed)

| Role | Login? | Can do |
|---|---|---|
| **Admin** | Yes, via `/admin` | Edit, add, delete any content. Upload images. Anyone you invite via Netlify is an admin. |
| **Visitor** | No login | Browse the site, fill the free-trial form (submits via WhatsApp), click WhatsApp/portal links. |

The "Login to Champions App" button on the site links to your actual Club Support App — that's a separate system with its own login.

---

## 📸 Image uploads

- Admin clicks the image field in any section, picks a file
- Image is stored in **GitHub** at `/images/uploads/`
- **Netlify serves it** via global CDN — fast everywhere
- Free up to ~1 GB of images and 100 GB monthly bandwidth
- All versions are kept forever (GitHub history)

---

## ✏️ Updating prices, offers, or running promotions

Common scenarios your client will hit:

**Run a flash sale** → edit the announcement bar in Site Settings. Live in 30 seconds.
**Change Football monthly price** → go to Sports → Football → update price field → save.
**Launch a new "Eid camp" offer** → go to Offers → New → fill in details → save.
**Add a new coach** → go to Coaches → New → upload photo, fill credentials → save.
**Mark a new news item as featured** → toggle the "Featured" switch on the news item. Only one at a time.

---

## 🛠 For your developer (not your client)

The site is pure HTML/JS — no build step, no framework lock-in. Everything is in `index.html` and content is fetched at runtime from `/content/`.

To add a new section type (e.g. "Tournaments" or "Gallery"):
1. Add a new collection to `admin/config.yml`
2. Add a render block in `index.html` that fetches and displays it
3. Push to GitHub → Netlify rebuilds automatically

---

## 💰 Costs

| Item | Cost |
|---|---|
| Domain (championsacademy.com) | ~$12/year |
| GitHub | Free |
| Netlify hosting + CMS | Free |
| **Total** | **~$1/month** |

That's it. No hidden fees, no monthly subscriptions, no per-admin charges.
