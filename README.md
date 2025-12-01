# JAVOOW — Portfolio

This repository contains a minimal static portfolio site for Javoow. The site is designed to be served as plain static files (e.g., GitHub Pages).

Preview locally

1. Open PowerShell and run:

```powershell
cd 'c:\Users\javon\Documents\GitHub\javoow.github.io'
python -m http.server 8000
```

2. Open http://localhost:8000 in your browser.

Deploy to GitHub Pages

- Push this repository to GitHub (branch `main`).
- In the repository settings on GitHub, go to Pages and set the source to the `main` branch.

If you want a custom domain, add a `CNAME` file with your domain and configure DNS accordingly. Tell me the domain and I can create the `CNAME` file for you.

Custom domain (javoow.com)

- I added a `CNAME` file containing `javoow.com` to this repository. GitHub Pages will use that value as the custom domain once DNS is configured and the Pages site finishes provisioning.

DNS records to add at your registrar/DNS provider

- For the apex/root domain (`javoow.com`) add these A records (GitHub Pages IPs):
	- `185.199.108.153`
	- `185.199.109.153`
	- `185.199.110.153`
	- `185.199.111.153`
- For the `www` subdomain add a CNAME record:
	- Host: `www` → CNAME → `javoow.github.io.`

Notes about HTTPS and propagation

- After you update DNS, GitHub Pages will automatically attempt to provision an SSL certificate for `javoow.com` and `www.javoow.com`. That can take a few minutes to a few hours.
- In the repository Settings → Pages, confirm the custom domain is `javoow.com` and that "Enforce HTTPS" is enabled once the certificate is issued.

If you use Cloudflare

- You can use Cloudflare in front of GitHub Pages, but for the apex domain you must either use Cloudflare's DNS with A records pointing to the GitHub Pages IPs (above) or use Cloudflare's CNAME flattening. When using Cloudflare, set the proxy (orange cloud) to OFF while GitHub Pages is issuing the SSL certificate — once HTTPS is active you may enable the proxy if desired, but be aware this changes how SSL is negotiated (Full/Full (strict) is recommended).

If you'd like, I can:
- Add a simple `www` redirect page, or
- Update the repo `README` further with screenshots for your registrar, or
- Walk through configuring Cloudflare step-by-step.
