# Stage 1: Discovery and Requirements

## Sheet Audit

| File | What it holds | Who keeps it | Problems found |
|---|---|---|---|
| website-orders-2026.csv | Website orders, July to September 2026, one row per order, with product code (SKU), discount, shipping and status | Exported from the website; Sam looks after it (not stated directly) | Duplicate orders, a blank row, cancelled and refunded orders mixed in, a product code missing from the stock sheet, customer names |
| marketplace-orders-q3.csv | Marketplace orders, July to September 2026, with the marketplace's fee and what Palmstone is paid out | Sam downloads it and pastes it in | Marketplace's own long product names, no product codes, price is the line total not the unit price |
| instagram-orders.csv | Orders taken by Instagram message, typed in by hand | Riley | Four date styles with no year, unclear day/month order, a missing date, five ways of saying "paid", free-text products and quantities, a likely duplicate |
| inventory-FINAL-v3.csv | Stock on hand and reorder level per product | Jules (warehouse, updates on Fridays) | Wall hangings missing on purpose, a discontinued product still listed, stale dates, returns not always added back |
| marketing-spend.csv | Weekly ad spend per channel | Riley (ads) and Sam (marketplace promo) | Weeks start on Saturday not Monday, one week missing, the same channel under three names, spend not linked to products |
| returns-log.csv | Returns, reason, refund amount, and whether it went back on the shelf | Sam | Every order number points to an order for a different product, missing order numbers, "insta" instead of a number, inconsistent names and Y/N values |

### Problems in Detail

Each problem names its evidence, so it can be checked in the sheet.

**website-orders-2026.csv**

- Duplicate rows: `W-1018` and `W-1045` each appear twice, identical.
- A completely blank row between `W-1031` and `W-1032`.
- Status mixes three kinds of order: 66 `Paid`, 5 `Cancelled` (`W-1001`, `W-1023`, `W-1031`, `W-1036`, `W-1051`) and 3 `Refunded` (`W-1002`, `W-1046`, `W-1064`). Dana: cancelled ones do not count.
- `W-1052` has a quantity of `2 ` with a trailing space.
- Product code `PL-012` (Macrame Wall Hanging) is not on the stock sheet. Jules explains why: wall hangings are made to order.
- Discount is a flat `$10.00` on 12 orders and blank on the rest; shipping is a separate column. Dana's sales figure excludes shipping and takes off discounts.
- The `Customer` column holds names. Dana does not want names on screen when she shows the bank.
- The 3 refunded orders do not appear in the returns log.

**marketplace-orders-q3.csv**

- Product names are the marketplace's own: `Rattan Pendant Lamp Shade Large`, `Linen Throw Blanket - Natural Flax`, `Stoneware Bud Vase Matte`. No product codes, so each must be matched by hand to the stock sheet.
- `sale_price` is the total for the line, not the unit price (`MK88208`: 2 blankets, `178.00`).
- The fee is 12% of the sale on every row. `payout` is what Palmstone keeps, which is the number Dana says matters most.
- Cleanest of the six: one date format (`2026-07-01`), no currency symbols, no customer names.

**instagram-orders.csv**

- Dates come in four styles, none with a year: `8/7`, `28 Jul`, `07/14`, `?`.
- Day and month order is mixed. `07/14` and `07/27` can only be month first; `17/7` and `20/8` can only be day first; `8/7`, `6/7`, `7/8`, `10/9`, `08/01`, `08/04` and `09/02` could be either.
- Mia's order has the date `?` and the note "not sure of date".
- "Paid" is written five ways: `Y`, `yes`, `Yes`, `no` and blank. Dana: only count paid orders.
- Amounts mix `$84`, `$42.00` and `98`.
- Product and quantity are free text in one column: `2x towels`, `1x sea salt candle`, `2x fig candles`.
- Mia's `candle + towel` is two products with one amount, so it cannot be split by product.
- Likely duplicate: Dev, `07/27`, sea salt candle, `$34`, appears twice.
- First names only, but still customer names.

**inventory-FINAL-v3.csv**

- Macrame wall hangings are missing on purpose (made to order), but they do sell on all three channels.
- `PL-000` Bamboo Tray is discontinued but still listed with 14 in stock. Jules: ignore it.
- `Last Updated` ranges from `02/05/2026` to `26/09/2026`; four products were last updated on `29/08/2026`, four weeks before the newest. Jules sometimes misses a week.
- Jules does not always add returned stock back, so some counts may be low.
- `PL-003` Rattan Lamp Shade: 3 in stock against a reorder level of 5, and Jules says its count was wrong recently. `PL-008` Stoneware Vase is at 0.
- Product names differ from the marketplace sheet (`Rattan Lamp Shade` against `Rattan Pendant Lamp Shade Large`).

**marketing-spend.csv**

- Every `Week starting` date is a Saturday (`04/07/2026` was a Saturday). Dana's week runs Monday to Sunday, so ad weeks and sales weeks do not line up.
- The week of `22/08/2026` is missing.
- One channel has three names: `Facebook + Instagram`, `FB/IG` and `Meta Ads`.
- `Marketplace promo` appears only in four weeks, kept by Sam, not Riley.
- Spend is per channel, not per product, so the August lamp shade push cannot be tied to lamp shade sales directly.

**returns-log.csv**

- Every order number that is filled in points to an order for a different product:
  - `W-1062` is logged as a lamp shade, but `W-1062` was a wall hanging ordered on `16/09/2026`, after the return date `30/07/2026`.
  - `W-1031` is logged as a serving board, but `W-1031` was a stoneware vase, and it was cancelled.
  - `MK88439` is logged as a serving board on `20/07/2026`, but it was a glass carafe ordered on `2026-08-27`.
  - `W-1013` is logged as a wall hanging, but it was bath towels.
  - `W-1005` is logged as a lamp shade, but it was a cushion cover.
  - `W-1012` is logged as a serving board, but it was linen throws.
- Five rows have no order number; three say `insta` instead of a number.
- Product names change case and wording: `Rattan Lamp Shade`, `rattan lamp shade`, `serving board`, `oak serving board`.
- `Restocked?` is `Y`, `N` or blank.
- Rattan lamp shades are 5 of the 14 returns, which backs up Dana's feeling.

## The Problem

[One or two sentences: what is painful today, and for whom]

## Users

| User | What they need from the dashboard |
|---|---|
| | |

## Must-Haves

1. [What it has to do]

## Qualities

[How well it has to do it: speed, devices, privacy, and so on]

## Open Questions

| Question | Answer or assumption | Source, or "assumption" |
|---|---|---|
| | | |

## Acceptance Criteria

| # | Must-have | Given, when, then |
|---|---|---|
| AC1 | | |

## Out of Scope

- [What you are deliberately not building]

## AI Did / I Decided

- AI did:
- I decided or corrected:
