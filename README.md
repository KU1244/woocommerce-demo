
4. Click **Place Order**
5. Order received page appears → **Order #67** (Status: Processing)
6. Check WooCommerce → Orders → Confirmed as paid
7. Stripe Dashboard (Test Mode) shows `$10.00 Succeeded`

### PayPal Sandbox Payment

1. On the checkout page, select **PayPal**
2. Login using a **Sandbox Buyer account**
3. Confirm the $10 payment
4. WooCommerce shows **Order #69 (Processing)**
5. PayPal Developer Dashboard → Business → Activity → "Payment received $10.00"

---

## Screenshots

| # | Description | File |
|---|--------------|------|
| 1 | Product page (Stripe + PayPal buttons) | 01-product.png |
| 2 | Stripe test checkout | 02-checkout-stripe.png |
| 3 | PayPal sandbox screen | 03-paypal-screen.png |
| 4 | Order received (#67) | 04-order-received.png |
| 5 | WooCommerce order list | 05-orders-list.png |
| 6 | Stripe dashboard showing success | 06-stripe-dashboard.png |

---

## Glossary

| Term | Meaning | Example |
|------|----------|---------|
| SSL | Secure HTTPS connection | `https://woo-express-demo.local` |
| Test Mode | Stripe testing environment | `pk_test_xxx` / `sk_test_xxx` |
| Link | Stripe one-click checkout | Email + saved card |
| Sandbox | PayPal fake test environment | Buyer / Business accounts |
| PRB | Payment Request Button | Google Pay / Apple Pay |
| Wizard | First-time setup guide in WooCommerce | Step-by-step initialization |

---

## Next Steps (for production)

- Switch Stripe from Test to Live keys
- Turn off PayPal Sandbox mode and connect a real account
- Add domain verification for Apple Pay
- Configure Stripe Webhooks (`/wc-api/wc_stripe`)
- Use SMTP plugin for reliable order emails

---

## Repository

GitHub: [https://github.com/KU1244/woocommerce-demo](https://github.com/KU1244/woocommerce-express-demo)
