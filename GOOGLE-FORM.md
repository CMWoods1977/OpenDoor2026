# The Google Form — what to create

This is the online twin of the tear-off slip. Build it once at
[forms.google.com](https://forms.google.com), then paste its link into `index.html`.

Set the form **title** to `An Open Door — my response` and the **description** to:

> The Parish of St Barnabas and St Paul with St Thomas the Martyr, Oxford.
> Thank you for supporting our churches. This takes about two minutes.

---

## The questions

Create these in order. "Short answer" and "Paragraph" are the plain text types;
"Checkboxes" allows more than one answer, "Multiple choice" allows only one.

| # | Question | Type | Required |
|---|---|---|---|
| 1 | Your name | Short answer | Yes |
| 2 | Address | Paragraph | Yes |
| 3 | Postcode | Short answer | Yes |
| 4 | Email address | Short answer | No |
| 5 | Telephone | Short answer | No |
| 6 | I would like to… | Checkboxes | Yes |
| 7 | How much will you give? | Short answer | No |
| 8 | How often? | Multiple choice | No |
| 9 | Starting from (date) | Date | No |
| 10 | Gift Aid declaration | Checkboxes | No |
| 11 | Anything you would like to tell us? | Paragraph | No |

### Question 6 — "I would like to…"

Checkboxes, required. Add a description: *Tick as many as apply.*

- I would like to start giving directly by Standing Order into the bank
- I would like to continue giving directly by Standing Order into the bank, but will increase my gift
- I would like to give a one-off donation
- I would like to talk to someone about leaving a legacy

### Question 7 — "How much will you give?"

Short answer. Description: *For example £20. Leave blank if you would rather not say yet.*

### Question 8 — "How often?"

Multiple choice: `Weekly` · `Monthly` · `Quarterly` · `Annually` · `This is a one-off gift`

### Question 10 — Gift Aid

Checkboxes, **not** required (people who do not pay tax must be able to leave it blank).

Question title: **Gift Aid — tick to add 25p to every £1, at no cost to you**

Set the question description to this exact wording:

> I want to Gift Aid this donation and any donations I make in the future or have made in the past four years to the PCC of the Ecclesiastical Parish of St Barnabas and St Paul with St Thomas the Martyr, Oxford. I am a UK taxpayer and understand that if I pay less Income Tax and/or Capital Gains Tax than the amount of Gift Aid claimed on all my donations in that tax year, it is my responsibility to pay any difference.

The single checkbox option should read:

- Yes, I am a UK taxpayer and I want the parish to claim Gift Aid on my giving

> **Worth checking.** HMRC requires specific information in a Gift Aid declaration, and a
> declaration made through a web form is valid provided the donor has seen and confirmed that
> wording. Ask the Treasurer to confirm this against the current guidance on gov.uk before the
> form goes live — the rules are occasionally revised, and a defective declaration invalidates
> the claim.

---

## Settings to change

Open **Settings** (the cog) and set:

- **Responses → Collect email addresses** — *Do not collect*, unless you want Google to force
  everyone to sign in. You are already asking for an email in question 4.
- **Responses → Limit to 1 response** — **off**. Leaving it on requires a Google account, which
  will exclude a good part of your congregation.
- **Presentation → Confirmation message** — replace the default with:

  > Thank you. Your response has been received, and someone from the parish will be in touch to
  > thank you properly. If you are setting up a standing order, please remember to do that
  > through your own online banking — we cannot do it for you.

- **Defaults → Make questions required by default** — off.

## Then

1. Click **Send**, choose the link icon, and copy the address.
2. Open `index.html`, scroll to the bottom, and paste it between the quotation marks on the
   `FORM_URL` line.
3. Save, commit, done. The yellow "not connected yet" notice disappears by itself and the form
   appears embedded in the page.

## Seeing the replies

In the form, open the **Responses** tab, then the green Sheets icon to send everything into a
spreadsheet. That sheet is what the Treasurer and the Gift Aid secretary will work from.

**One thing to agree before you launch:** this sheet holds names, addresses and giving
intentions, which is exactly the sort of data the PCC should be careful with. Decide who has
access to it, keep that list short, and make sure it is not shared more widely than the people
who actually need it.
