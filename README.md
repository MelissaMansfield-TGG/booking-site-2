# book.thegerontechnologygroup.com

The booking page for The Gerontechnology Group. One HTML file, no scripts, no third party requests. Everything it needs is in this folder.

```
index.html          the page
CNAME               tells GitHub Pages which domain this is (do not rename or edit)
assets/logo.png     the GTG lockup
assets/og-card.png  the preview image LinkedIn and Facebook show when the link is shared
assets/fonts/       Source Sans 3, self hosted so the page never calls Google
```

## Publishing on the new GitHub account

Do these in order. Steps 1 to 3 put the page online at a github.io address. Step 4 moves the real domain to it.

### 1. Create the repository

1. Sign in to the new account on github.com.
2. Click the **+** in the top right, then **New repository**.
3. Name it `booking` (any name works). Set it to **Public**. Leave every other option unchecked. Click **Create repository**.

### 2. Upload the files

1. On the empty repository page, click **uploading an existing file**.
2. Drag the whole contents of this folder in: `index.html`, `CNAME`, `README.md`, and the `assets` folder. Keep the folder structure; `index.html` must be at the top level, not inside a subfolder.
3. Click **Commit changes**.

### 3. Turn on GitHub Pages

1. In the repository, click **Settings**, then **Pages** in the left column.
2. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to **main**, folder to **/ (root)**. Click **Save**.
3. Because the `CNAME` file is in the repo, the **Custom domain** box fills in with `book.thegerontechnologygroup.com` on its own. If GitHub shows a warning that the domain is not yet pointed here, that is expected until step 4.
4. Tick **Enforce HTTPS** once it becomes available (it can take a few minutes after DNS changes).

### 4. Point the domain at the new account

This is the one step that actually moves the site. Until it is done, the old page keeps showing.

1. Log in wherever the DNS for `thegerontechnologygroup.com` is managed (the registrar, or Cloudflare if it is in front of the WordPress site).
2. Find the record for `book`. It is a **CNAME** record currently pointing to `mippy1974.github.io`.
3. Change its value to `NEW-USERNAME.github.io`, where NEW-USERNAME is the new GitHub account name, exactly as it appears in the profile URL. Nothing else on the record changes.
4. Save. Changes usually show within an hour.

If GitHub says the domain "is already taken" or asks you to verify it, go to the new account's **Settings → Pages → Add a domain**, enter `thegerontechnologygroup.com`, and add the TXT record it gives you at the DNS provider. That proves the new account owns the domain. The old account had it verified; the new one has to as well.

### 5. Clean up

Once `https://book.thegerontechnologygroup.com` shows the new page with the padlock, the old repository on the mippy1974 account can be deleted. The privacy page is still hosted there (`mippy1974.github.io/privacy/`) and the footer links to it, so either leave that repo in place or move the privacy page too and update the link in `index.html`.

## Editing later

Open `index.html` on github.com, click the pencil icon, change the text, and commit. The page rebuilds itself within a minute or two. Prices, the email address, and the credential line each appear more than once, so search the file when changing one of them.

## What the page does not do

- Visit counting uses GoatCounter (site code gtg, dashboard at gtg.goatcounter.com). It uses no cookies and stores no personal information. It is the only outside request the page makes.
- Booking runs through Calendly. The free fit call and the paid Technology Triage Call buttons link to the Calendly event pages. Two email links remain as a backup.
