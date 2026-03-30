# 🚀 How to Add a New Chrome Extension

Follow these exact steps every time you launch a new extension.

---

## Step 1 — Build the Extension

Create a new folder inside `ChromeExtension/`:

```
ChromeExtension/
  My_New_Extension/
    manifest.json
    popup/
    background.js
    icons/
    ...
```

In `manifest.json`, set the homepage URL:
```json
"homepage_url": "https://atul0016.github.io/as-extensions/my-new-extension/"
```

In the popup's `popup.js`, set the payment URL:
```js
this.PAYMENT_URL = 'https://as-extension.netlify.app/pay.html?ext=my-new-extension';
```

> **Note:** The `ext` value must match exactly what you use in the Netlify env vars below.
> Use lowercase with hyphens: e.g. `my-new-extension`

---

## Step 2 — Add Website & Privacy Policy

Create a new folder in the root of `ChromeExtension/`:

```
ChromeExtension/
  my-new-extension/
    index.html            ← landing page for users
    privacy-policy.html   ← required by Chrome Web Store
    terms-of-service.html
```

Copy `pixel-ruler/privacy-policy.html` as a template and update the extension name.

Push to GitHub → Privacy Policy URL will automatically be live at:
```
https://atul0016.github.io/as-extensions/my-new-extension/privacy-policy.html
```

---

## Step 3 — Add Pricing to Netlify (< 1 minute)

Go to → **Netlify → as-extension site → Site Configuration → Environment Variables**

Add these 2 (or 3) variables:

```
MY_NEW_EXTENSION_PRICE_INR = 149
MY_NEW_EXTENSION_PRICE_USD = 1.99
MY_NEW_EXTENSION_NAME      = My New Extension Premium
```

> **KEY FORMAT RULE:** Take the `ext` name, uppercase it, and replace hyphens with underscores.
> Example: `my-new-extension` → `MY_NEW_EXTENSION`

Hit **Save** → **Trigger Deploy**. Done. No code changes needed in the backend ever.

---

## Step 4 — Add Card to Showcase Page

Open `d:\CUSTOMS\as-extension\index.html` and add a new card in the `.cards` section:

```html
<div class="card">
  <div class="card-header">
    <span class="card-icon">🛠️</span>
    <div class="card-title">My New Extension</div>
    <p class="card-desc">Short description of what it does.</p>
  </div>
  <div class="card-features">
    <ul>
      <li>Feature one</li>
      <li>Feature two</li>
      <li>Feature three</li>
    </ul>
  </div>
  <div class="card-footer">
    <div class="badge-pill">One-Time Purchase</div>
    <div class="price-row">
      <span class="price-inr">₹149</span>
      <span class="price-usd">/ $1.99</span>
    </div>
    <p class="price-label">Lifetime access · No subscription</p>
    <a class="btn-primary" href="/pay.html?ext=my-new-extension">
      Unlock My New Extension →
    </a>
  </div>
</div>
```

Push to GitHub.

---

## Step 5 — Zip & Upload to Chrome Web Store

Run this command in PowerShell from `D:\CUSTOMS\ChromeExtension\`:

```powershell
Compress-Archive -Path My_New_Extension\* -DestinationPath my-new-extension-ready.zip -Force
```

Then go to → [Chrome Web Store Developer Console](https://chrome.google.com/webstore/devconsole)
- Upload `my-new-extension-ready.zip`
- Set **Privacy Policy URL** to:
  `https://atul0016.github.io/as-extensions/my-new-extension/privacy-policy.html`

---

## Summary — What You Need Per Extension

| Task | Where |
|---|---|
| Extension code | `ChromeExtension/My_New_Extension/` |
| Privacy policy page | `ChromeExtension/my-new-extension/privacy-policy.html` |
| Pricing config | Netlify → `as-extension` → Environment Variables |
| Showcase card | `as-extension/index.html` |
| Chrome Web Store upload | `.zip` file → Developer Console |

---

## Repository Map

| Repo | Purpose | URL |
|---|---|---|
| `as-extensions` | Website + Privacy Policies (GitHub Pages) | `atul0016.github.io/as-extensions` |
| `as-extension` | Universal Payment Backend (Netlify) | `as-extension.netlify.app` |
| `smart-capture-extension` | Smart Capture source code (Private) | GitHub only |
| `pixel-ruler-extension` | Pixel Ruler source code (Private) | GitHub only |
