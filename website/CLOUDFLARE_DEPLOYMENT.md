# Cloudflare Pages Deployment Guide

Deploy TK ABA Kalikajar website to Cloudflare Pages with custom domain `https://tkabakalikajar.sch.id`

---

## Prerequisites

- GitHub repository: `TK-ABA-Kalikajar/website`
- Domain: `tkabakalikajar.sch.id` (purchased from Domainesia)
- Cloudflare account (free plan is sufficient)

---

## Part 1: Cloudflare Pages Setup

### Step 1: Create Cloudflare Account
1. Go to https://dash.cloudflare.com/sign-up
2. Create account with your email
3. Verify your email address

### Step 2: Connect GitHub Repository
1. Go to **Cloudflare Dashboard** → **Workers & Pages**
2. Click **Create application** → **Pages**
3. Click **Connect to Git**
4. Click **Connect GitHub** and authorize Cloudflare
5. Select repository: `TK-ABA-Kalikajar/website`

### Step 3: Configure Build Settings

| Setting | Value |
|---------|-------|
| **Project name** | `tkabakalikajar` |
| **Production branch** | `main` |
| **Framework preset** | Astro |
| **Build command** | `npm run build` |
| **Build output directory** | `dist` |
| **Root directory** | `website` |

**Environment Variables (click "Add variable"):**
| Variable | Value |
|----------|-------|
| `NODE_VERSION` | `18` |

### Step 4: Deploy
1. Click **Save and Deploy**
2. Wait for build to complete (1-2 minutes)
3. Once complete, you'll get a URL like: `https://tkabakalikajar.pages.dev`
4. Test this URL to make sure your site works

---

## Part 2: Add Domain to Cloudflare

### Step 5: Add Your Domain to Cloudflare
1. In Cloudflare Dashboard, click **Add a site** (top right)
2. Enter: `tkabakalikajar.sch.id`
3. Click **Continue**
4. Select **Free plan** → Click **Continue**
5. Cloudflare will scan for existing DNS records
6. Review records and click **Continue**
7. **Important:** Cloudflare will show you 2 nameservers like:
   ```
   ada.ns.cloudflare.com
   bob.ns.cloudflare.com
   ```
8. **Copy these nameservers** - you'll need them for the next step

---

## Part 3: Configure Domainesia

### Step 6: Change Nameservers at Domainesia
1. Login to Domainesia: https://my.domainesia.com
2. Go to **Domain** → Click on `tkabakalikajar.sch.id`
3. Find **Nameserver** or **Kelola Nameserver** section
4. Change from Domainesia's default nameservers to Cloudflare's:
   - **Nameserver 1:** `ada.ns.cloudflare.com` (use yours from Step 5)
   - **Nameserver 2:** `bob.ns.cloudflare.com` (use yours from Step 5)
5. Click **Simpan** / **Save**
6. Wait for DNS propagation (can take 1-48 hours, usually faster)

### Step 7: Verify Domain in Cloudflare
1. Go back to Cloudflare Dashboard
2. Click on your domain `tkabakalikajar.sch.id`
3. Click **Check nameservers now**
4. Once verified, status will change to **Active** (green checkmark)

> **Note:** You can proceed to the next steps while waiting. The custom domain won't work until nameservers propagate, but you can set everything up.

---

## Part 4: Connect Domain to Cloudflare Pages

### Step 8: Add Custom Domain to Your Pages Project
1. Go to **Workers & Pages** → Click on your project (`tkabakalikajar`)
2. Click **Custom domains** tab
3. Click **Set up a custom domain**
4. Enter: `tkabakalikajar.sch.id`
5. Click **Continue** → **Activate domain**
6. Repeat for `www.tkabakalikajar.sch.id`:
   - Click **Set up a custom domain** again
   - Enter: `www.tkabakalikajar.sch.id`
   - Click **Continue** → **Activate domain**

---

## Part 5: Configure HTTPS

### Step 9: Enable HTTPS Settings
1. In Cloudflare Dashboard, click on your domain `tkabakalikajar.sch.id`
2. Go to **SSL/TLS** (left sidebar)
3. Set encryption mode to **Full (strict)**
4. Go to **SSL/TLS** → **Edge Certificates**
5. Enable these options:
   - **Always Use HTTPS** → Toggle ON
   - **Automatic HTTPS Rewrites** → Toggle ON

### Step 10: Verify Everything Works
After DNS propagation completes:

1. Visit `https://tkabakalikajar.sch.id`
2. Check for padlock icon in browser address bar
3. Try `http://tkabakalikajar.sch.id` - should redirect to HTTPS
4. Try `https://www.tkabakalikajar.sch.id` - should also work

---

## Verification Checklist

- [ ] Site loads at `https://tkabakalikajar.sch.id`
- [ ] Padlock icon appears (SSL certificate active)
- [ ] `http://` redirects to `https://`
- [ ] `www.tkabakalikajar.sch.id` works
- [ ] All pages load: `/`, `/tentang`, `/profil`, `/guru-staff`, `/siswa`, `/galeri`, `/kontak`
- [ ] Images load properly
- [ ] Mobile responsive works

---

## Automatic Deployments

Once set up, Cloudflare Pages will automatically:
- Deploy when you push to `main` branch
- Create preview deployments for pull requests
- Keep deployment history (you can rollback anytime)

---

## Troubleshooting

### Build Failed
- Check that **Root directory** is set to `website`
- Check that `NODE_VERSION` environment variable is `18`
- View build logs in Cloudflare Pages dashboard

### Custom Domain Not Working
- Verify nameservers were changed correctly at Domainesia
- Wait for DNS propagation (up to 48 hours)
- In Cloudflare Pages, check custom domain status

### HTTPS Not Working / Certificate Error
- Ensure domain shows **Active** in Cloudflare
- Wait a few minutes for SSL certificate to provision
- Check SSL/TLS mode is set to **Full (strict)**

### Mixed Content Warnings
- Enable **Automatic HTTPS Rewrites** in SSL/TLS settings

---

## Useful Links

- Cloudflare Dashboard: https://dash.cloudflare.com
- Domainesia: https://my.domainesia.com
- Cloudflare Pages Docs: https://developers.cloudflare.com/pages
- Astro Deployment Guide: https://docs.astro.build/en/guides/deploy/cloudflare/
