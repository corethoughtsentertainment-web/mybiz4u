[README.md](https://github.com/user-attachments/files/30136255/README.md)
# DealPilot AI

A production-minded Next.js starter for an affiliate deal site with:

- eBay Browse API deal search and affiliate URLs
- Demo data when no credentials are configured
- Newsletter capture using Resend
- Protected OpenAI-powered buying-guide drafting
- Affiliate disclosure, privacy starter, sitemap, robots, responsive dark design

## Run locally

```bash
cp .env.example .env.local
npm install
npm run dev
```

Open `http://localhost:3000`. The site works immediately in demo mode.

## Add live eBay deals

1. Create an eBay Developers account and application keys.
2. Join eBay Partner Network and obtain your campaign ID.
3. Add `EBAY_CLIENT_ID`, `EBAY_CLIENT_SECRET`, and `EBAY_CAMPAIGN_ID` to `.env.local`.
4. Restart the app.

The Browse API route requests `itemAffiliateWebUrl` using the affiliate context header. Never expose the client secret in browser code.

## Add email subscribers

1. Create a Resend account.
2. Verify a domain.
3. Add `RESEND_API_KEY`, `RESEND_FROM_EMAIL`, and `NEWSLETTER_OWNER_EMAIL`.

For a larger list, connect the form to a dedicated audience/database system rather than relying only on notification emails.

## Add AI content generation

1. Add `OPENAI_API_KEY`.
2. Set a long random `ADMIN_SECRET`.
3. Visit `/admin`, enter the secret, and generate a draft.
4. Fact-check, edit, and add genuine expertise before publishing.

The endpoint is server-side so keys are not exposed. For a public launch, add real authentication, rate limiting, and a database/CMS.

## Deploy on Vercel

1. Upload this folder to a GitHub repository.
2. Import the repository into Vercel.
3. Add every environment variable in Vercel Project Settings → Environment Variables.
4. Set `NEXT_PUBLIC_SITE_URL` to your final HTTPS domain.
5. Deploy.

## Before monetizing

- Replace the placeholder privacy policy with terms appropriate to your business and jurisdiction.
- Add a contact page and business identity.
- Follow each affiliate program’s current rules, brand-use rules, price-display requirements, and disclosure requirements.
- Do not scrape retailer pages unless their terms explicitly permit it.
- Do not auto-publish unreviewed AI articles. Thin or inaccurate content will harm trust and search performance.
- Connect analytics and Search Console.

## Revenue reality

The software provides the infrastructure, not guaranteed income. Reaching $5,000/month depends on qualified traffic, conversion rate, commission rates, content quality, and affiliate approval. Focus on one high-intent category first, publish useful comparison content, build the email list, and measure clicks and revenue per visitor.
