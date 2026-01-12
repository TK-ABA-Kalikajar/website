# Vercel Deployment Guide

Deploy TK ABA Kalikajar website to Vercel with custom domain `https://tkabakalikajar.sch.id`

---

## Prerequisites

- GitHub repository: `TK-ABA-Kalikajar/website`
- Domain: `tkabakalikajar.sch.id` (purchased from Domainesia)
- Vercel account (free plan is sufficient)

---

## Part 1: Vercel Setup

### Step 1: Create Vercel Account
1. Go to https://vercel.com/signup
2. Sign up with GitHub (recommended)
3. Authorize Vercel to access your GitHub

### Step 2: Import Project
1. Click **Add New...** → **Project**
2. Select repository: `TK-ABA-Kalikajar/website`
3. Vercel auto-detects Astro framework

### Step 3: Configure Build Settings
Vercel usually auto-detects these, but verify:

| Setting | Value |
|---------|-------|
| **Framework Preset** | Astro |
| **Root Directory** | `website` |
| **Build Command** | `npm run build` |
| **Output Directory** | `dist` |

### Step 4: Deploy
1. Click **Deploy**
2. Wait for build (usually under 1 minute)
3. You'll get a URL like: `https://website-xxx.vercel.app`

---

## Part 2: Add Custom Domain in Vercel

### Step 5: Add Domain to Vercel
1. Go to your project in Vercel Dashboard
2. Click **Settings** → **Domains**
3. Enter: `tkabakalikajar.sch.id`
4. Click **Add**
5. Vercel will show DNS configuration instructions
6. Repeat for `www.tkabakalikajar.sch.id`

---

## Part 3: Configure DNS at Domainesia

### Step 6: Add DNS Records

Login to Domainesia and add these DNS records:

| Type | Name/Host | Value/Target | TTL |
|------|-----------|--------------|-----|
| **A** | `@` | `76.76.21.21` | 3600 |
| **CNAME** | `www` | `cname.vercel-dns.com` | 3600 |

**How to add in Domainesia:**
1. Login to https://my.domainesia.com
2. Go to **Domain** → Click on `tkabakalikajar.sch.id`
3. Find **DNS Management** / **Kelola DNS** / **Zone Editor**
4. Delete any existing A records for root domain (`@`)
5. Add the records from the table above
6. Save changes

### Alternative: Using Vercel Nameservers
If you prefer full Vercel control, change nameservers at Domainesia to:
- `ns1.vercel-dns.com`
- `ns2.vercel-dns.com`

(Not recommended unless you want Vercel to manage all DNS)

---

## Part 4: Verify & HTTPS

### Step 7: Wait for DNS Propagation
- Usually takes 5-30 minutes
- Can take up to 48 hours in some cases
- Check status in Vercel → Settings → Domains

### Step 8: Verify HTTPS
Vercel automatically:
- Provisions SSL certificate (Let's Encrypt)
- Enables HTTPS
- Redirects HTTP to HTTPS

Once DNS is verified:
1. Visit `https://tkabakalikajar.sch.id`
2. Check for padlock icon
3. Try `http://` - should redirect to `https://`

---

## Verification Checklist

- [ ] Site loads at `https://tkabakalikajar.sch.id`
- [ ] Padlock icon appears (SSL active)
- [ ] `http://` redirects to `https://`
- [ ] `www.tkabakalikajar.sch.id` works
- [ ] All pages load: `/`, `/tentang`, `/profil`, `/guru-staff`, `/siswa`, `/galeri`, `/kontak`
- [ ] Images and favicon load properly
- [ ] Mobile responsive works

---

## Automatic Deployments

Vercel automatically:
- Deploys when you push to `main` branch
- Creates preview deployments for pull requests
- Keeps deployment history with instant rollback

---

## Troubleshooting

### Domain Not Working
- Verify DNS records are correct in Domainesia
- Wait for DNS propagation
- Check Vercel Dashboard → Domains for status
- Use https://dnschecker.org to verify DNS propagation

### Build Failed
- Check build logs in Vercel Dashboard
- Verify `Root Directory` is set to `website`
- Test locally with `npm run build`

### HTTPS/SSL Issues
- Wait for Vercel to provision certificate (automatic)
- Ensure domain is verified in Vercel
- Check for mixed content warnings

### 404 Errors on Pages
- Verify build output includes all pages
- Check `astro.config.mjs` has correct `site` URL

---

## Useful Links

- Vercel Dashboard: https://vercel.com/dashboard
- Domainesia: https://my.domainesia.com
- DNS Checker: https://dnschecker.org
- Vercel Domains Docs: https://vercel.com/docs/projects/domains
- Astro on Vercel: https://docs.astro.build/en/guides/deploy/vercel/

---

## Quick Reference

| Service | URL |
|---------|-----|
| Vercel Dashboard | https://vercel.com/dashboard |
| Production Site | https://tkabakalikajar.sch.id |
| Vercel Preview | https://website-xxx.vercel.app |
