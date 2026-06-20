# Rule 52 Launch Notes

This repo contains the public IVA site plus the public Rule 52 product page at `/rule52/`.

## Includes

- Existing IVA site files.
- Standalone Rule 52 landing page.
- Rule 52 logo, favicon, and social preview assets.
- Starter and Pro document preview images.
- Navigation/footer links from the main IVA site to Rule 52.

## Deliberately not included

- Cloudflare Worker generator source code.
- Stripe secret keys.
- Stripe webhook signing secret.
- Resend API key.
- Product ZIP files.
- Customer entitlement records.

The generator logic lives server-side in the Cloudflare Worker at `generator.ivasolution.com`. Do not publish Worker source in a public GitHub Pages repo if you want to keep the generator logic protected.

## Public product page

`https://ivasolution.com/rule52/`

## Generator app

`https://generator.ivasolution.com`

## Stripe links used on the page

Starter, $49:
`https://buy.stripe.com/dRm8wQ2fifSM1SmfTJfrW09`

Pro, $149:
`https://buy.stripe.com/bJedRag684a454y6j9frW08`

Consultant Client-Use License, $499:
`https://buy.stripe.com/9B65kEaLO7mg8gKbDtfrW07`

Agency License, $999/year:
`https://buy.stripe.com/00w28sg685e868C0YPfrW06`

All live Stripe Payment Links should redirect after payment to:

`https://generator.ivasolution.com/access?session_id={CHECKOUT_SESSION_ID}`

## Pre-launch check

- `/rule52/` loads.
- Rule 52 logo appears.
- Starter and Pro preview images appear.
- All four Stripe links open the correct checkout page.
- `https://generator.ivasolution.com/health` loads.
- `https://generator.ivasolution.com/recover` loads.
- Cloudflare Worker has `ENTITLEMENTS` KV binding.
- Cloudflare Worker has live `STRIPE_SECRET_KEY` and `STRIPE_WEBHOOK_SECRET` secrets.
- Stripe webhook endpoint is active: `https://generator.ivasolution.com/stripe-webhook`.
