# Adventure Classics Fleet Finder

A phone app for scoring 1946–48 Willys CJ2A Jeeps at the seller's curb. It turns the Adventure Classics 100-point checklist into a reconditioning estimate, an opening offer, a walk-away price, a Strong / Moderate / Weak buy rating, a resale check, and a Jeep Report that can be texted, emailed or shared.

It is a Progressive Web App (PWA): plain HTML, CSS and JavaScript, no build step, no server code, no accounts. It installs to the home screen and works offline after the first visit.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app |
| `manifest.webmanifest` | Name, icon and colors used when installed |
| `sw.js` | Service worker that caches the app for offline use |
| `icons/` | Home-screen icons |

## Hosting on GitHub Pages (for Ethan)

1. Create a new public repository, for example `fleet-finder`, in the same account as the Quabbin Scoring App.
2. Upload every file in this folder to the repository root, keeping the `icons/` folder.
3. Go to **Settings → Pages**. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to `main`, folder `/ (root)`, and click **Save**.
4. After a minute or two the app is live at `https://<account>.github.io/fleet-finder/`. Send that link to anyone who should use it.

It must be served over HTTPS (GitHub Pages does this automatically) for installing and offline use to work.

## Publishing an update

1. Replace the changed files in the repository.
2. In `sw.js`, change `VERSION` (for example `ff-v1` → `ff-v2`) so phones drop the old cached copy.
3. Commit. Phones pick up the update the next time the app is opened with signal.

## Installing on a phone

**iPhone:** open the link in Safari → Share button → **Add to Home Screen** → Add.

**Android:** open the link in Chrome → ⋮ menu → **Install app** (or **Add to home screen**) → Install.

Open it once with signal after installing so it is cached for offline use.

## Where data lives

Everything a user enters (saved Jeeps, settings, cost defaults) is stored only in that phone's browser storage. Nothing is sent to a server, and users cannot see each other's Jeeps. To share a Jeep, use **Send Jeep Report** on the Offer tab. Uninstalling the app or clearing the browser's site data erases that phone's saved Jeeps.

## Default numbers

Budget $10,000 target / $12,000 ceiling, mechanical labor $85/hr, body labor $35/hr, 15% contingency, $600 + 6 hr Fleet Buy kit, $300 bill-of-sale allowance, $10,250 finished market value, 5% cost to sell. Part costs and hours are rough starting estimates. Every user can change all of these in Settings on their own phone.
