# parilabs-webfront

One-page website for **Parilabs** (engineering consultancy), hosted on GitHub Pages at <https://parilabs.org>.

## Files

- `index.html` — page content (services, portfolio, about, contact)
- `styles.css` — styling
- `CNAME` — tells GitHub Pages to serve the site on `parilabs.org`

## Contact form

The form posts to [FormSubmit](https://formsubmit.co) (no account needed), which emails submissions to `sales@parilabs.org`.
The **first** submission triggers a one-time activation email to that address — click the link in it to start receiving messages.

## Local preview

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy (GitHub Pages)

1. Push to `main`.
2. GitHub → repo **Settings → Pages** → Source: *Deploy from a branch*, Branch: `main` / `(root)` → Save.
3. Under **Custom domain** enter `parilabs.org` → Save. Once DNS check passes, tick **Enforce HTTPS**.

## DNS (Namecheap → Domain List → Manage → Advanced DNS)

Delete the default `CNAME www → parkingpage.namecheap.com` and `URL Redirect @` records, then add:

| Type    | Host | Value                 |
|---------|------|-----------------------|
| A       | @    | 185.199.108.153       |
| A       | @    | 185.199.109.153       |
| A       | @    | 185.199.110.153       |
| A       | @    | 185.199.111.153       |
| CNAME   | www  | pmiros.github.io.     |

Check propagation: `dig parilabs.org +short` should return the four IPs above.
