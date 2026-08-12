# madvylage.com

Public one-pager for MadVylage (Dylan Martinez Consulting): business
presence + the privacy/SMS policy that carrier and platform compliance
reviews (Twilio A2P 10DLC, toll-free verification) expect to find.

Static, no build step: `index.html`, `privacy.html`, `CNAME`.

## Deploy (GitHub Pages, free)

1. Create a **public** GitHub repo (e.g. `MaDDylan/madvylage.com`), push
   these files to `main`.
2. Repo Settings -> Pages -> Source: `main` / root. The `CNAME` file in
   this folder sets the custom domain automatically.
3. At Porkbun (madvylage.com -> DNS), **delete the URL-forward to
   l.ink** and add:

   | Type  | Host | Answer                  |
   |-------|------|-------------------------|
   | A     | (root) | 185.199.108.153      |
   | A     | (root) | 185.199.109.153      |
   | A     | (root) | 185.199.110.153      |
   | A     | (root) | 185.199.111.153      |
   | CNAME | www  | maddylan.github.io      |

4. Back in repo Settings -> Pages: confirm the custom domain shows
   verified, then check **Enforce HTTPS** (appears after the cert
   issues, usually < 1 hour).

## Notes

- This domain is also the future public face of the MadVylage
  self-hosted stack (Track 2); when that lands, this static site moves
  behind the same reverse proxy and this repo becomes its content.
- Keep the SMS section of `privacy.html` accurate: operational alerts
  to opted-in staff only, STOP/HELP honored, no number sharing. Twilio
  campaign registrations should point at
  `https://madvylage.com/privacy.html`.
