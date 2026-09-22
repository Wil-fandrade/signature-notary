# Signature Notary

Responsive one-page website for a professional notary service in Chesterfield, Virginia.

## Features

- Animated three-scene hero slideshow
- Responsive service, about, process, testimonial, and appointment sections
- Accessible slideshow controls and reduced-motion support
- Embedded hero imagery for a self-contained static deployment

## Local preview

Open `index.html` directly or serve the folder with any static web server.

## Cloudflare Pages

Use `/` as the root directory and leave the build command empty.

Production site: https://signature-notary.pages.dev/

To deploy the static files from `main`:

```sh
deploy_dir=$(mktemp -d)
cp index.html _headers "$deploy_dir/"
npx --yes wrangler pages deploy "$deploy_dir" --project-name signature-notary --branch main
```

This project uses direct uploads; pushing to GitHub does not automatically deploy it.

If Wrangler reports `UNABLE_TO_GET_ISSUER_CERT_LOCALLY` on this Mac, use the
existing system certificate bundle before running Wrangler:

```sh
export NODE_EXTRA_CA_CERTS=/etc/ssl/cert.pem
npx --yes wrangler whoami
```

This keeps TLS certificate verification enabled. If authentication is required,
run `npx --yes wrangler login` in the same terminal.

## Before accepting real appointments

Replace the placeholder phone number and email address in `index.html`, and connect the appointment form to an approved form-processing service or backend.
