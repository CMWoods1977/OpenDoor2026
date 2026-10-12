# An Open Door — stewardship page

A single web page for the 2026 stewardship campaign of the Parish of St Barnabas and St Paul
with St Thomas the Martyr, Oxford. One HTML file, no build step, no dependencies.

```
index.html       the page
leaflet.pdf      the printed leaflet, offered as a download
GOOGLE-FORM.md   what to put in the Google Form
README.md        this file
```

---

## Do this first

**1. Make the Google Form.** Follow `GOOGLE-FORM.md`. It takes about fifteen minutes.

**2. Connect it.** Open `index.html`, scroll to the bottom, and find this line:

```js
const FORM_URL = "PASTE_YOUR_GOOGLE_FORM_LINK_HERE";
```

Paste your form link between the quotation marks and save. Until you do, the page shows a
yellow notice where the form belongs — visible to anyone looking at the site, so do this
before you tell people the address.

**3. Check it.** Double-click `index.html` to open it in a browser. The form should appear
embedded in the page and the gold button should open it in a new tab.

---

## Publishing it on GitHub Pages

1. On [github.com](https://github.com), click **New repository**. Name it something like
   `open-door`. Set it to **Public** — GitHub Pages will not serve a private repo on a free
   account. Tick nothing else, and click **Create**.
2. On the new repository page, click **uploading an existing file**.
3. Drag in all four files from this folder. Scroll down, click **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment*, set **Source** to
   `Deploy from a branch`, **Branch** to `main`, folder `/ (root)`. Click **Save**.
5. Wait two or three minutes, then reload that Settings → Pages screen. Your address appears
   at the top, in the form:

   ```
   https://YOUR-USERNAME.github.io/open-door/
   ```

That address is what goes on the pew sheet, in the newsletter, and in the email to the
congregation.

### Changing something later

Click the file in GitHub, click the pencil icon, edit, then **Commit changes**. The live site
updates within a minute or two. Everything on the page — the figures, the dates, the bank
details, the wording — is plain text in `index.html` and safe to edit.

### A tidier address

If the parish already owns a domain, you can point something like `giving.sbarnabas.org.uk` at
this page: add a `CNAME` file in the repository containing that one line, then add a CNAME
record with your domain provider pointing to `YOUR-USERNAME.github.io`. Your website host can
do this in a few minutes if it is unfamiliar territory.

The simplest alternative, if you would rather not: ask whoever maintains sbarnabas.org.uk to
add a menu link called **Giving** that points at the GitHub Pages address.

---

## Notes on what is in the page

- **Everything is in one file.** The CSS is inline, there are no fonts or scripts loaded from
  elsewhere, and nothing tracks anyone. The page works offline and will still work in ten
  years.
- **The bank details are public**, exactly as they are in the printed leaflet. The page carries
  a short warning telling people to telephone the Parish Office if they are ever asked to pay
  into a different account. Church payment-redirection fraud is common enough to be worth that
  line; please leave it in.
- **It is designed for a phone**, because most people will arrive by tapping a link or scanning
  a code in church rather than sitting at a desk.
- **It prints sensibly** if anyone wants a paper copy — the form and buttons drop away.

## Worth doing before launch

- Add a **photograph**. The page is handsome but entirely typographic. A picture of the open
  west door or the new organ case, dropped in below the first paragraph, would lift it
  considerably. Any `.jpg` in this folder can be shown with
  `<img src="yourphoto.jpg" alt="The west door of St Barnabas, open" style="width:100%;border-radius:3px;margin:20px 0">`.
- Get a **QR code** made for the address and put it on the pew sheet and the poster. Plenty of
  free generators will do this once you know the URL.
- Ask one person who is not confident with computers to try it on their phone and report back.
  That test is worth more than any amount of checking by people who already know how it works.
