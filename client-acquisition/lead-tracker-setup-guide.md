# Lead Tracker — Google Sheets Setup Guide
**Owner: Lois | Last Updated: April 2026**

---

## Step 1: Import the CSV into Google Sheets

1. Go to [sheets.google.com](https://sheets.google.com) and create a new spreadsheet
2. Name it: **PLM Creative — Lead Tracker**
3. Go to **File → Import → Upload** and select `lead-tracker-template.csv`
4. Choose: Import location = **Replace current sheet**, Separator = **Comma**
5. Click **Import data**

---

## Step 2: Format the Header Row

1. Click the row number **1** to select the entire header row
2. **Bold** it: `Ctrl+B` (or `Cmd+B` on Mac)
3. Set background colour to **#0d0d0d** (dark ink) and text colour to **#f5f0e8** (cream)
4. Set font size to **11**, font to **Arial**
5. **Freeze the header row:** View → Freeze → 1 row

---

## Step 3: Set Column Widths

| Column | Width |
|--------|-------|
| Name | 160px |
| Company | 160px |
| Platform Found | 130px |
| Sector | 140px |
| Service Tier | 110px |
| LinkedIn URL | 220px |
| Email | 200px |
| Status | 130px |
| Notes | 260px |
| Date Added | 110px |
| Last Contact Date | 130px |
| Follow-up Date | 120px |

To set width: right-click the column letter → **Resize column** → enter pixel width.

---

## Step 4: Create the Status Dropdown (Data Validation)

1. Click the **Status column header (H)** to select the entire column
2. Go to **Data → Data validation**
3. Set **Criteria** to: **List of items**
4. Enter exactly: `Yet to Reach Out,Cold,Warm,Hot,Client`
5. Tick **Show dropdown list in cell**
6. Set **On invalid data** to: **Show warning**
7. Click **Save**

---

## Step 5: Apply Conditional Formatting (Colour Coding)

Go to **Format → Conditional formatting**. Apply each rule to the **Status column (H2:H1000)**:

| Status | Background Colour | Text Colour | Hex Codes |
|--------|-------------------|-------------|-----------|
| Yet to Reach Out | #9E9E9E (grey) | #FFFFFF (white) | BG: 9E9E9E / Text: FFFFFF |
| Cold | #4A90D9 (blue) | #FFFFFF (white) | BG: 4A90D9 / Text: FFFFFF |
| Warm | #F5A623 (yellow) | #1A1A1A (dark) | BG: F5A623 / Text: 1A1A1A |
| Hot | #27AE60 (green) | #FFFFFF (white) | BG: 27AE60 / Text: FFFFFF |
| Client | #1A1A1A (black) | #FFFFFF (white) | BG: 1A1A1A / Text: FFFFFF |

For each rule:
1. Click **+ Add another rule**
2. Format cells if: **Text is exactly** → type the status value
3. Set the formatting style (background + text colour as above)
4. Click **Done**

---

## Step 6: Create the Service Tier Dropdown

1. Click the **Service Tier column header (E)** to select the entire column
2. Go to **Data → Data validation**
3. Set Criteria to: **List of items**
4. Enter: `Tier 1 - Brand Storytelling,Tier 1 - Automation,Tier 2 - Content Strategy,Tier 2 - Web App,Tier 3 - Pitch Deck`
5. Click **Save**

---

## Step 7: Create the Platform Found Dropdown

1. Click the **Platform Found column (C)**
2. **Data → Data validation → List of items**
3. Enter: `LinkedIn,Instagram,Facebook Ads Library,Referral,Twitter/X,Website,Other`
4. Click **Save**

---

## Step 8: Save Filter Views

These are the views Lois uses daily. Go to **Data → Filter views → Create new filter view** for each:

**View 1: "Hot Leads"**
- Filter Status column = **Hot**
- Name the view: `🔥 Hot Leads`

**View 2: "Follow-up Today"**
- Filter Follow-up Date column = **today** (use a custom formula: `=L2=TODAY()`)
- Name the view: `📅 Follow-up Today`

**View 3: "Tier 1 Prospects"**
- Filter Service Tier contains **Tier 1**
- Status = **Yet to Reach Out** OR **Cold**
- Name the view: `Tier 1 — Ready to Contact`

**View 4: "This Week's Outreach"**
- Filter Date Added = this week
- Name the view: `📤 This Week Added`

---

## Step 9: Add the Weekly Metrics Tab

1. At the bottom of the sheet, click **+** to add a new tab
2. Name it: **Weekly Metrics**
3. Set up the following structure:

```
Week of | Prospects Added | DMs Sent | Replies | Reply Rate | Calls Booked | Deals Closed | Revenue ($) | Top Converting Tier | Notes
```

Lois fills this in every **Friday at 4pm Lagos time**.

---

## Step 10: Share the Sheet

1. Click **Share** (top right)
2. Add Seun's email with **Viewer** access (he reviews, doesn't edit)
3. Add Lois's email with **Editor** access
4. Copy the sheet link and save it in the team's shared workspace

---

## Column Definitions (Reference)

| Column | What Goes Here |
|--------|----------------|
| Name | First and last name of the prospect |
| Company | Their company or startup name |
| Platform Found | Where Lois found them (LinkedIn, IG, etc.) |
| Sector | Their industry (e.g. Fintech, Agri, Logistics, Media) |
| Service Tier | Which PLM service they're a fit for |
| LinkedIn URL | Direct URL to their LinkedIn profile |
| Email | Work email if found (via LinkedIn, website, or Hunter.io) |
| Status | Current pipeline stage — use the dropdown only |
| Notes | Key observations: what they post about, pain points mentioned, last conversation context |
| Date Added | Date Lois added them to the tracker (dd/mm/yyyy) |
| Last Contact Date | Date of most recent DM or email sent |
| Follow-up Date | Date Lois should next contact them |

---

## Rules Lois Must Follow

- **Never change a status backwards** without logging why in Notes
- **Every DM sent = update Last Contact Date that same day**
- **No prospect sits on "Yet to Reach Out" for more than 3 days** after being added
- **Hot leads get flagged to Seun within 1 hour** of a positive reply
- **Status goes to "Client" only when a contract is signed and deposit received**
