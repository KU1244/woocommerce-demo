markdown
---

## 💳 Payment Test Log (Hands-on)

### Stripe (Test Mode)
- Product: Demo Product ($10)
- Steps:
  1) Add to Cart → Checkout → **Place Order**
  2) **Order received: #67 / Status: Processing**
  3) WooCommerce → Orders: **Paid** is confirmed
  4) Stripe Dashboard (Test): shows **$10.00 Succeeded**
- Why: Prove the full **card payment path** works and the WooCommerce order status updates correctly.

### PayPal (Sandbox)
- Steps:
  1) Choose **PayPal** on Checkout
  2) Login with **Sandbox Buyer**
  3) Confirm $10 payment
  4) WooCommerce → **Order #69 (Processing)**
  5) PayPal Developer Dashboard → Business → Activity: shows **Payment received $10.00**
- Why: End-to-end check in **PayPal Sandbox** (buyer → store → business account).

---

## 🧩 Plugins / Settings Snapshot

- **EWWW Image Optimizer** — WebP + Lazy Load ON  
  *Why*: Reduce image weight and speed up first paint.

- **WP Fastest Cache** — Minify HTML/CSS/JS, Gzip, Preload  
  *Exclude*: `cart/`, `checkout/`, `my-account/`  
  *Why*: Speed up with static cache while protecting dynamic pages.

- **Rank Math SEO** — Sitemap ON (`/sitemap_index.xml`), Product/Article schema  
  *Why*: Structured data + auto meta for basic SEO.

- **WooCommerce Stripe Gateway** — Test Mode, PRB (Google Pay / Apple Pay) ready  
  *Why*: One-tap checkout options; better mobile conversion.

- **WooCommerce PayPal** — Sandbox  
  *Why*: PayPal users can convert quickly.

---

## 🔐 Security / Compliance Notes

- **SSL (HTTPS)** required on all checkout pages.  
- **Stripe Webhooks**: enable for production → `.../wc-api/wc_stripe` (verify signature).  
- **Email delivery**: use an **SMTP plugin** (SendGrid/SES, etc.) for reliable order emails.  
- **Apple Pay**: upload domain verification file (`/.well-known/apple-developer-merchantid-domain-association`).

---

## 🧪 Quick Troubleshooting

| Symptom | Common Cause | Fix |
|---|---|---|
| Stripe stays “Unpaid” | Webhook not set / failing | Add production webhook, enable signing secret |
| No emails after payment | PHP mail poor deliverability | Install SMTP plugin, send test |
| Blank Cart/Checkout | Page cached by mistake | Exclude `cart/`, `checkout/`, `my-account/` in cache |
| Apple Pay not visible | Domain not verified / no HTTPS | Verify domain, ensure HTTPS, test on supported browser |
| PayPal sandbox fails | Wrong balance/currency/role | Check Sandbox Buyer & Business settings |

---

## ✅ Go-Live Checklist

- [ ] Stripe: switch to **Live keys** (`pk_live_...` / `sk_live_...`)  
- [ ] Stripe: add **production webhooks** (+ signature verification)  
- [ ] PayPal: **turn off Sandbox** and connect live account  
- [ ] Apple Pay: **domain verification** done  
- [ ] SMTP: DKIM/SPF/DMARC set on sending domain  
- [ ] Cache/CDN: avoid double compression with CDN  
- [ ] Speed proof: add **PageSpeed Before/After** table

---

## 🧠 Plain-English Glossary

| Term | Meaning | Example |
|------|--------|---------|
| SSL | Secure HTTPS connection | `https://your-store.com` |
| Test Mode | Stripe test environment | `pk_test_xxx` / `sk_test_xxx` |
| Link | Stripe one-click checkout | Email + saved card |
| Sandbox | PayPal fake test environment | Buyer / Business accounts |
| PRB | Payment Request Button | Google Pay / Apple Pay |
| Webhook | Auto callback from a service | Stripe → WooCommerce order update |
| Lazy Load | Load images only when needed | Images below the fold load on scroll |

---

## 🗓️ Changelog

- **2025-10-29 (JST)**  
  - Image optimization / Cache / Rank Math setup  
  - Stripe (Test) and PayPal (Sandbox) verified: **#67** / **#69**  
  - Checkout pages excluded from cache

---

## 📸 Screenshots

| # | Description                | Image |
|---|----------------------------|-------|
| 1 | Product page               | ![Product](./screenshots/wordpress-home.png) |
| 2 | Stripe test checkout       | ![Stripe Checkout](./screenshots/checkout-stripe.png) |
| 3 | PayPal sandbox screen      | ![PayPal](./screenshots/paypal-screen.png) |
| 4 | Order received / Orders    | ![Orders List](./screenshots/orders-list.png) |
| 5 | Stripe dashboard (success) | ![Stripe Dashboard](./screenshots/stripe-dashboard.png) |
| 6 | WP + WooCommerce summary   | ![WP + WooCommerce](./screenshots/wordpress-woocommerce.png) |


---

## 🔗 Repository

GitHub: https://github.com/KU1244/woocommerce-demo