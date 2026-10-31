# book.round2.sg

Branded address for the Round2 booking engine's guest pages, so guests never see `workers.dev`:
`book.round2.sg/done?ref=…` (booking confirmation, where HitPay sends guests after paying), `/find` ("View your booking"),
`/b/<code>` (link in SimplyBook's confirmation email). The address with nothing after it shows "View your booking".

- `index.html` / `404.html` (identical): show `https://round2-book.donttelldadyet.workers.dev` + the same path inside a full-page
  frame. The engine's pages post `{r2:'page', path, title}` to this page when they change, so the address bar follows.
  Engine source: round2sg-home `worker/round2-book.js` (`PUBLIC_BOOK`).
- `CNAME`: `book.round2.sg`. DNS in Wix › Domains › round2.sg › Manage DNS: CNAME `book` → `donttelldadyet-prog.github.io`.
- GitHub › Settings › Pages: deploy from branch `main`, folder `/ (root)`, custom domain `book.round2.sg`, Enforce HTTPS on.
- Same idea as `cue.round2.sg` (repo round2-cue). Webhooks (HitPay, SimplyBook) stay on `workers.dev` – guests never see them.
