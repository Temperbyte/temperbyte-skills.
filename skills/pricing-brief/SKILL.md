---
name: pricing-brief
description: Turns a real estate agent's comparable sales (comps) into a pricing brief with correct price-per-square-foot math, outlier handling, a suggested list price range with its method shown, a confidence level, and a plain-language explanation for the seller. Use when an agent pastes comps, MLS data or a CMA and asks for a pricing recommendation, a list price range, a CMA summary or talking points for a listing appointment.
---

# Pricing Brief

The agent pastes a subject property and a set of comparables. Return a brief the agent can trust at a listing appointment: every number traceable to the comps, every exclusion explained, and a seller-facing explanation.

The agent sets the price. You do the math, show the method, and say how confident the data allows anyone to be. This is not an appraisal.

## Privacy first

- Do not ask for or repeat personal details of sellers, buyers or tenants (names, phone numbers, email addresses, finances or personal circumstances). Describe the property and the transaction only. If the paste contains such details, leave them out of the output and add one line at the top: "Tip: remove client names and contact details before pasting."
- Example data in your replies must be invented, never a real client's data.

## Step 1: Sort the inputs

For the **subject**, collect: address or area, property type, bedrooms, bathrooms, square footage, lot size, year built, condition and notable features. If square footage is missing, ask for it before doing price-per-square-foot math; nothing else in this skill works without it.

For each **comp**, collect: status (sold, pending, active, expired/withdrawn), price (sale price for sold, list price otherwise), square footage, beds/baths, sale or list date, days on market, distance or area, condition notes, and original list price if given.

Rules:
- **Never invent a comp or a missing number.** If a comp lacks square footage, keep it in the table marked "no sq ft" and leave it out of the per-square-foot math.
- **Only sold comps set value.** Pending comps support it (price may not be final). Active listings show competition, not value. Expired or withdrawn listings show where the market said no.
- If the agent gave no sale dates, say so; you cannot judge whether comps are current.

## Step 2: Screen the sold comps

Use a code tool for every calculation if one is available.

Exclude a sold comp from the value math, and say why, when any of these apply:
- Square footage differs from the subject by more than about 25%.
- It is a different property type (condo versus single-family, for example).
- The notes describe a non-market sale: foreclosure, short sale, estate or auction, sale between family members, a full gut-renovation candidate, or anything the agent flags as unusual.
- Its price per square foot is far from the others: more than about 20% from the median of the remaining comps. Show the number that triggered the exclusion.

Never exclude a comp quietly. Every exclusion appears in the Comp Table with its reason.

## Step 3: Do the math

On the comps that pass screening:
- **Price per square foot** for each comp (price ÷ square footage).
- **Median** price per square foot. Use the median, not the average, because one odd sale moves an average a lot. Also show the low and high.
- **Indicated value:** subject square footage × median $/sq ft, and subject square footage × the low and high $/sq ft.
- **List-to-sale ratio** (sale price ÷ original list price) for each sold comp that has an original list price, and the median.
- **Median days on market** for sold comps.
- Round final prices to the nearest $1,000; keep $/sq ft to whole dollars.

Then adjust **direction only, not dollar amounts**, for meaningful differences you can see in the data (condition, updates, garage, lot size, beds/baths). Say which way each difference pushes the subject within the range. Do not invent dollar adjustments; only an appraiser or the agent's own judgment should put a number on them.

## Step 4: Set the range and confidence

- **Suggested list range:** start from the indicated value at the median, place the subject within the low–high band using the direction adjustments, and give a range roughly 3–5% wide centered on that placement point. If the low–high band is narrower than 3%, center the range on the indicated value at the median. Never add a "negotiation room" premium or any other ad-hoc markup. Show the arithmetic in one line, and make sure the stated placement matches the range (if the subject sits "at or above the median", the low end of the range is not below the median value).
- **Expected sale price:** the median list-to-sale ratio applied to the range tells the agent where offers are likely to land. Say this in one line when ratios are available.
- **Market signals:** active listings priced above the range with high days on market, and expired listings, are evidence that pricing above the range has not worked. Say so when present.
- **Confidence:**
  - **High:** 4 or more usable sold comps, all recent, similar, and within a tight $/sq ft band.
  - **Medium:** 3 usable comps, or a wide $/sq ft spread, or some comps older than about 6 months.
  - **Low:** fewer than 3 usable sold comps, or dates missing. With low confidence, say plainly that the range is weak and what data would firm it up.

If the agent or seller has a target price, compare it to the range with numbers: dollars and percent above the indicated value at the median, and above the top of the range. State what the comps say about listings priced there. Be direct and respectful; do not inflate the range to meet a target.

If the target is above the range, add a short fallback plan for a seller who still insists, so the agent has a script: list no higher than the agent judges defensible, agree in writing on a price review after a set period (for example 14 days) with a reduction into the range if showings or offers are weak, and note that the agent may also decline the listing. Do not invent the likely outcome of overpricing in dollars; point to the actives and expireds in the data instead.

## Step 5: Write the output

Use exactly these headings, in this order:

### Bottom Line
Two or three lines: suggested list range, confidence level, and the single biggest reason.

### Comp Table
One row per comp: address or ID, status, price, sq ft, $/sq ft, days on market, list-to-sale ratio if known, and **Used / Excluded (reason) / Context only** for active, pending, and expired listings.

### The Math
Median, low and high $/sq ft from the used comps; indicated value at each; median list-to-sale ratio and days on market; the one-line arithmetic for the suggested range.

### Where the Subject Sits
Bullets: each difference between the subject and the comps, and whether it pushes toward the low or high end. No dollar amounts.

### Market Signals
What actives, pendings and expireds suggest about pricing.

### Seller Talking Points
Four to six plain-language bullets the agent can say out loud at the appointment. Read each one as if speaking to the seller; rewrite anything that would sound confusing. No jargon without a short explanation. If the seller's target is above the range, include one respectful, numbers-based point about it. Only claim the range "leaves room to negotiate" if that is true at both ends.

### If the Seller Insists
Only when the seller's target is above the range: the fallback plan from Step 4, in two or three bullets.

### Data Gaps
Up to five items that would raise confidence or change the range (missing dates, missing sq ft, unknown condition of comps, too few comps, seller concessions). For condos, include HOA dues and any special assessments compared with the comps.

## Rules

- Every number in the brief must come from the agent's data or the calculations above. Recheck that the figures in Bottom Line, The Math and Seller Talking Points match each other before finishing.
- **No unsupported qualifiers.** Do not call comps "recent", "nearby" or "similar", or the subject "updated", unless the data says so (a sale date, a distance, a stated feature). This applies with extra force in Seller Talking Points, which the agent reads aloud.
- **Fair housing:** describe properties and transactions only. Never describe neighborhoods by who lives there, safety, school ratings or "desirability" of residents. Name a school or amenity only if the agent provided it, and never rate it.
- Include this line at the end: "This brief is a comparative market analysis based on the data provided, not an appraisal."

## Review reminder

End every output with this line, exactly: *Draft made with AI. Check every number, fact and recommendation before you use it.*
