# Sign-up Sheet → CSV
**El Cerrito Trail Trekkers · event roster tool**

Converts paper sign-up sheets (photos or scanned PDFs) into a formatted CSV ready to import into Mailchimp or a spreadsheet.

---

## How to use it

### First time only

1. **Open the app** at `https://YOUR-USERNAME.github.io/ectt-signup/signup-to-csv.html`
2. **Get an Anthropic API key**
   - Go to [console.anthropic.com](https://console.anthropic.com) and create a free account
   - Click **API Keys** → **Create Key** → copy the key (starts with `sk-ant-…`)
3. **Paste the key** into the API Key box in the app and click **Save key**
   - The key is stored only in your browser — you won't need to enter it again on this device

### Every time

1. Take a photo of the sign-up sheet (or use a scanned PDF)
2. Drag the file into the app, or click to upload
   - Accepted formats: JPG, JPEG, PNG, PDF
3. Click **Extract & build CSV**
4. Review the preview table to spot any errors
5. Click **Download CSV** — the file is ready to import

---

## Output columns

| Column | Description |
|---|---|
| Email Address | |
| First Name | |
| Last Name | |
| Address | |
| Phone | |
| Signup Date | From the event date at the top of the sheet |
| Signup Event | From the event name at the top of the sheet |
| Event Source Raw | Verbatim "How did you hear?" response |
| Event Source | Normalized version (see below) |

### Event Source normalization

The app uses judgment to consolidate free-text "How did you hear?" responses into consistent values:

| Normalized value | Examples it matches |
|---|---|
| word of mouth | friend, neighbor, family, a person's name, someone told me |
| El Cerrito website | El Cerrito website, city website, ecbike.org |
| social media | Facebook, Instagram, NextDoor, online |
| email | newsletter, mailing list, listserv |
| flyer / poster | flyer, poster, sign, handout |
| organizer | organizer, staff, I organized it |
| other | anything else |

---

## Tips for good results

- **Good lighting matters** — photos taken in daylight or under bright indoor light extract more accurately than dim or shadowy shots
- **Shoot straight on** — minimize angle/skew; the sheet should fill most of the frame
- **One sheet per file** — if a sign-up sheet spans two pages, upload them as separate files; they'll be combined into one CSV
- **Review the preview** — Claude reads handwriting well but occasional errors happen, especially with ambiguous letters or very light ink; spot-check emails in particular before importing to Mailchimp

---

## Cost

The app uses the Anthropic Claude API, which charges per use. Processing one sign-up sheet image typically costs **less than $0.01**. A full season of Trail Trekkers events would run a few cents total.

You can monitor usage and set spending limits at [console.anthropic.com](https://console.anthropic.com).

---

## Privacy

- Sign-up sheet images are sent directly from your browser to Anthropic's API for processing — they are not stored or logged by this app
- API keys are stored only in your browser's local storage and are never transmitted anywhere except to Anthropic
- See [Anthropic's privacy policy](https://www.anthropic.com/privacy) for how they handle API data

---

## Updating the app

If the HTML file is updated, replace `signup-to-csv.html` in the GitHub repository:
1. Go to the repository on github.com
2. Click on `signup-to-csv.html` → click the pencil (edit) icon → or drag a new file to replace it
3. Click **Commit changes** — the live URL updates automatically within a minute

---

*Built for the El Cerrito Trail Trekkers using the Claude API.*
