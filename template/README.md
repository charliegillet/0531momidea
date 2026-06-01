# Local Business Website Template

A single-file, mobile-friendly website template you can clone for any local business
in **5–15 minutes**. Everything lives in one `index.html` — no build tools, no frameworks,
no dependencies. Open it in a browser to preview instantly.

It already includes the things local customers actually want:
- ✅ Mobile-responsive (looks great on phones — where most of their customers are)
- ✅ **Click-to-call** buttons everywhere + a floating call button on mobile
- ✅ Services grid, About, Hours, Reviews, Photo gallery, Contact, Google Map embed
- ✅ One **CONFIG block** at the top — edit values, save, refresh. That's it.

---

## How to make a site for a new client (the fast workflow)

1. **Copy the folder.** Duplicate `template/` and rename it, e.g. `clients/joes-tacos/`.
2. **Open `index.html`** in a text editor.
3. **Edit the `CONFIG = { ... }` block** near the top:
   - `business`, `tagline`, `subtagline`
   - `phone` (display) + `phoneRaw` (digits only, like `+15551234567`)
   - `email`, `address`
   - `primary` / `accent` / `dark` — their brand colors (use their logo's colors)
   - `hours` — set each day; leave `""` for closed days
   - `about` — one short paragraph
   - `services` — list with emoji icon + title + description
   - `reviews` — **copy straight from their Google/Facebook reviews**
   - `gallery` — image URLs (their photos, or free ones from unsplash.com / pexels.com)
   - `mapEmbed` — see below; leave `""` to hide the map
   - `facebook` / `instagram` — leave `""` to hide
4. **Edit the two lines in `<head>`** — the `<title>` and `<meta description>`. These are
   what show up in Google search results, so include the business + town +
   service (e.g. `Joe's Tacos — Best Tacos in Austin, TX`).
5. **Save, open in a browser, done.** Send the file/link to the client for approval.

> 💡 You can knock out a site in well under an hour. Make a couple of industry
> variants (restaurant, salon, trades) and you're mostly just swapping text.

---

## Getting the Google Map embed
1. Go to [Google Maps](https://maps.google.com), search the business address.
2. Click **Share** → **Embed a map** → **Copy HTML**.
3. From that HTML, copy just the `src="..."` URL and paste it into `mapEmbed`.

---

## Adding real photos
- Easiest: ask the client, or pull from their existing Facebook/Google listing.
- Free stock: [Unsplash](https://unsplash.com), [Pexels](https://pexels.com). Right-click
  → copy image address, paste the URL into the `gallery` array.
- For best speed, host images on the same site (drop them in the folder and use
  `"photo1.jpg"` instead of a URL).

---

## Putting it live (free or near-free hosting)

Pick whichever you're comfortable with:

| Option | Cost | Best for |
|---|---|---|
| **Netlify Drop** | Free | Drag-and-drop the folder at app.netlify.com/drop → instant live URL. Great for **previews**. |
| **GitHub Pages** | Free | Push to a repo, enable Pages. You already have a repo set up. |
| **Cloudflare Pages** | Free | Connect a repo or upload; fast global hosting. |
| **Their own domain** | ~$12/yr domain | Point the domain at any of the above once they've **paid**. |

### Payment-protection tip (matches your playbook)
Host the preview on a **temporary URL** (Netlify Drop subdomain or a GitHub Pages path).
Let them review and approve there. Only **after they pay** do you connect their real
domain and hand over access. You keep the keys until you're paid.

---

## Files
- `index.html` — the template (also the Acme Plumbing demo as shipped).
- `example-restaurant.html` — a second pre-filled example (a taco shop) to show range
  and prove the same template works across industries.

Open both in a browser to see how different the same template looks with different
config — that's your demo when you're on the phone.
