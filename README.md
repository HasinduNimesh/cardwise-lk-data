# CardWise LK offers data

A daily snapshot of credit card offers that Sri Lankan banks and finance
companies list on their own websites, as one file: [`offers.json`](offers.json).
The CardWise LK app downloads it.

> **Unofficial.** Not run by, affiliated with, or endorsed by any bank. It is a
> convenience index that points back to each issuer's own page. Offers change
> and pages are sometimes wrong. **Always confirm the current terms with the
> bank before spending.** Nothing here is financial advice.

## About the file

- Refreshed automatically once a day by a scraper that reads each issuer's
  public offers page. It identifies itself honestly, obeys `robots.txt`, and
  makes only a handful of requests a day.
- `null` means unknown, never zero. There is deliberately no minimum spend or
  maximum discount: those are in each offer's terms, so every offer links to
  the issuer's own page (`detailUrl` / `sourceUrl`).
- `sources[].status` says whether each issuer was read successfully. If a read
  fails, that issuer's previous offers are kept and marked with the time of the
  last good read.
- Readers should hide offers whose `validTo` is in the past and any with
  `validityConflict: true`.

An issuer that wants its offers removed can ask and they will be taken out.

## Licence

No licence has been chosen yet. The offers are the issuers' public
information, linked back to their source.
