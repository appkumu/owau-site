# owauapp.com — waitlist site

Static site for GitHub Pages: waitlist landing page, privacy policy and support page.

## Files

- `index.html` — home page: hero, how it works, app preview, features, portal dates, FAQ, waitlist
- `privacy.html` — privacy policy (DRAFT: fill in every [bracketed] item) — App Store "Privacy Policy URL"
- `terms.html` — terms of use (DRAFT: fill in every [bracketed] item) — needed for subscriptions
- `support.html` — support / FAQ page (App Store "Support URL")
- `404.html` — "page not found" page
- `og-image.png` — preview image shown when the link is shared
- `apple-touch-icon.png` — icon when someone saves the site to their home screen
- `style.css` — shared styles in Owau brand colors
- `CNAME` — tells GitHub Pages to serve the site at owauapp.com

## 1. Connect the waitlist form (Kit)

1. Create a free account at kit.com.
2. Grow → Landing Pages & Forms → Create → Form → Inline. Name it "Owau waitlist".
3. Publish it, choose "HTML", and copy the form ID from the action URL
   (`https://app.kit.com/forms/1234567/subscriptions` → `1234567`).
4. In `index.html`, find `WAITLIST_ENDPOINT` near the bottom and replace `YOUR_FORM_ID`.
5. Submit a test email and check it shows up in Kit under Subscribers.

Using a different tool? Replace `WAITLIST_ENDPOINT` with its form-post URL. The form sends
the email as both `email_address` and `email`, so it works with Kit and Formspree as-is.

## 2. Publish on GitHub Pages

1. Create a repo (e.g. `owau-site`) and upload these files to the root.
2. Settings → Pages → Source: "Deploy from a branch" → `main` / root → Save.
3. Custom domain: `owauapp.com` (already set by the `CNAME` file).
4. After DNS is live, tick "Enforce HTTPS".

## 3. DNS at Network Solutions

| Type  | Host | Value                           |
|-------|------|---------------------------------|
| A     | @    | 185.199.108.153                 |
| A     | @    | 185.199.109.153                 |
| A     | @    | 185.199.110.153                 |
| A     | @    | 185.199.111.153                 |
| CNAME | www  | YOURGITHUBUSERNAME.github.io    |

Remove any existing parking/forwarding record on `@`.

## 4. Before App Store submission

- Fill in every [bracketed] item in `privacy.html` and `support.html`.
- Set up `support@owauapp.com` (Network Solutions email forwarding to your inbox works).
- Use `https://owauapp.com/privacy.html` and `https://owauapp.com/support.html` in App Store Connect,
  and link `https://owauapp.com/terms.html` in the app description / paywall.

## 5. After launch

- Replace the waitlist forms with an "Download on the App Store" badge (from Apple's marketing tools).
- Add `<meta name="apple-itunes-app" content="app-id=YOUR_APP_ID">` in `index.html` for the Safari app banner.
- Swap the CSS phone mockups for real screenshots if you like.
