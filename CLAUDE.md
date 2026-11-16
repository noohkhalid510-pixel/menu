# Shop menu: how to update

This repo is the shop's live menu website (GitHub Pages, published from `main`):
- Menu: https://noohkhalid510-pixel.github.io/menu/
- Counter tablet QR screen: https://noohkhalid510-pixel.github.io/menu/#counter

The owner is not technical. They will say things like "Blue Razz is out of stock",
"add X for $20" or "change the price of Y". Make the change, publish it, and confirm
in one or two plain sentences. Don't ask them to touch GitHub.

## Where things are

Everything is in `index.html`, in the block marked `EDIT YOUR SHOP HERE`:
- `OPEN_HOUR`: hour (24h clock) the daily QR code changes. `MINUTES`: how long each scan lasts (currently 10).
- `ITEMS`: one line per product: `name`, `category`, `price`, `desc`, `status`, optional `isNew`, `color`.
  - `status`: `"in"` (in stock), `"low"` (only a few left), `"out"` (sold out, shown faded with a "Sold out" badge).
  - Categories come from the items, in the order they first appear. A new category name creates a new filter button.
- Keep `MENU_URL` as is. It works out the site address by itself.
- Changing `SECRET` cancels today's QR code immediately (only if the owner asks).

## Publishing

1. Edit `index.html`.
2. Commit with `git config user.name Claude` and `git config user.email noreply@anthropic.com`.
3. Push straight to `main`. The site updates in about 1 to 2 minutes.

The owner should not see any Claude sign-in. The site must stay a single self-contained `index.html`.
