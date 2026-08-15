# edbanti.com

Static personal site. One file: `index.html`. No build step.

## Deploy

Hosted on GitHub Pages from the `main` branch of this repo. Push to `main` and it goes live in ~1 minute.

```
git add -A && git commit -m "update" && git push
```

## DNS (Squarespace domain dashboard)

Apex A records -> GitHub Pages:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```
`www` CNAME -> `<username>.github.io`

Do not touch the MX or SPF TXT records - those carry Microsoft 365 email for the domain.

The `CNAME` file in this repo tells GitHub Pages the custom domain. Do not delete it.

## Local preview

```
python3 -m http.server 8000
```
then open http://localhost:8000
