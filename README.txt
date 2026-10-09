GOLDENROD — landing page
========================

What's in this folder
---------------------
index.html           the page
goldenrod.html   the app itself (what the Download button hands out)
shots/               screenshots used on the page (+ og.jpg for link previews)
favicon.svg, icons/  the tab icon in a few sizes

Before you publish
------------------
Open index.html in a text editor and fill in the three lines near the top:

    payUrl:    "https://buy.stripe.com/....."   <- your payment link (see below)
    suggested: "$10"
    contact:   "you@example.com"                 <- optional
    version:   "1.0"  /  updated: "October 2026" <- bump these with each new goldenrod.html

Until payUrl is set, the "Pay what you like" buttons show as dashed and do nothing.

To replace a screenshot, drop a new image over the file in shots/ with the same
name (hero.webp, two-up.webp, comment.webp, thread.webp, read.webp, log.webp).
Any size works; 2200px wide looks sharp on Retina screens.

To ship a new version of the app, replace goldenrod.html. The Download
button always serves whatever file is there.

Hosting (free)
--------------
GitHub Pages — durable, free, no bandwidth worries for a 2 MB file:
  1. github.com -> New repository -> name it goldenrod, Public, Create.
  2. "Add file" -> "Upload files" -> drag in index.html, goldenrod.html,
     README.txt and the shots folder -> Commit.
  3. Settings -> Pages -> Source: "Deploy from a branch", Branch: main, / (root) -> Save.
  4. A minute later the page is live at https://YOURNAME.github.io/goldenrod/
     (Settings -> Pages shows the exact URL.) Updates: upload the changed file again.

Netlify Drop — even simpler, drag-and-drop:
  app.netlify.com/drop -> drag this whole folder onto the page -> done.
  Sign in (free) so the site doesn't expire; you get a random URL you can rename.

Either host lets you attach your own domain later.

Link previews: the og:image / og:url / canonical lines in index.html point at
https://geraldgordinier.github.io/goldenrod/ — change them if the address changes.

Taking payment (pay what you like)
----------------------------------
The page gives the download away unconditionally; paying is a separate, optional
button. Pick one of these for the button's link:

Stripe Payment Link (recommended; looks the most professional, money goes straight
to your bank, no platform cut — just card fees of about 2.9% + 30c):
  1. dashboard.stripe.com -> create a free account (individual / sole proprietor is fine).
  2. Payment Links -> "+ New" -> choose "Customers choose what to pay".
  3. Title "Goldenrod", preset amount 10, minimum 1 (Stripe won't take $0 —
     that's what the free Download button is for). Create link.
  4. Paste the link into payUrl.
  5. Send payers to the download: open the link in Stripe -> Edit -> "After payment"
     -> "Don't show confirmation page" -> redirect to
     https://YOURNAME.github.io/goldenrod/thanks.html
     That page starts the download on arrival. (Optional: Settings -> Emails ->
     turn on receipts for successful payments.)

Ko-fi (fastest to set up, 0% platform fee on tips; card/PayPal fees still apply):
  ko-fi.com -> create a page -> set your "coffee" price to $10 -> paste your
  ko-fi.com/yourname link into payUrl.

If you'd rather not host anything yourself: itch.io hosts the file and the page,
has a "$0 or donate" mode with a suggested price and a "No thanks, just take me
to the downloads" link, and lets you set its cut to 0%. Gumroad does the same
with "$0+" pricing and collects every downloader's email (handy for announcing
updates) but keeps 10% + 50c of each sale plus card fees.
